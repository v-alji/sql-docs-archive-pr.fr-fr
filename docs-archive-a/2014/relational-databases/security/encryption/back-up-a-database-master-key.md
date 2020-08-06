---
title: Sauvegarder une clé primaire de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], exporting
ms.assetid: 7ad9a0a0-6e4f-4f7b-8801-8c1b9d49c4d8
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 9a66d28fea8289719d3efb2351409e0f14379ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709087"
---
# <a name="back-up-a-database-master-key"></a><span data-ttu-id="e7cfb-102">Sauvegarder une clé primaire de base de données</span><span class="sxs-lookup"><span data-stu-id="e7cfb-102">Back Up a Database Master Key</span></span>
  <span data-ttu-id="e7cfb-103">Cette rubrique explique comment sauvegarder une clé principale de base de données dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7cfb-103">This topic describes how to back up a database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="e7cfb-104">La clé principale d'une base de données permet de chiffrer d'autres clés et certificats à l'intérieur d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-104">The database master key is used to encrypt other keys and certificates inside a database.</span></span> <span data-ttu-id="e7cfb-105">Si celle-ci est supprimée ou endommagée, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] risque de ne pas pouvoir déchiffrer ces clés, et les données chiffrées qui les utilisent seront perdues.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-105">If it is deleted or corrupted, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may be unable to decrypt those keys, and the data encrypted using them will be effectively lost.</span></span> <span data-ttu-id="e7cfb-106">C'est pourquoi vous devez sauvegarder la clé principale de la base de données et stocker la sauvegarde dans un emplacement sécurisé, en dehors de votre lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-106">For this reason, you should back up the database master key and store the backup in a secure off-site location.</span></span>  
  
 <span data-ttu-id="e7cfb-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="e7cfb-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e7cfb-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="e7cfb-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e7cfb-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e7cfb-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e7cfb-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e7cfb-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="e7cfb-111">Pour sauvegarder une clé principale de base de données à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7cfb-111">To back up a database master key using Transact-SQL</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7cfb-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e7cfb-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e7cfb-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="e7cfb-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e7cfb-114">La clé principale doit être ouverte et, par conséquent, déchiffrée avant d'être sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="e7cfb-115">Si elle est chiffrée avec la clé principale de service, il n'est pas nécessaire que la clé principale soit ouverte explicitement.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened.</span></span> <span data-ttu-id="e7cfb-116">En revanche, si la clé principale est chiffrée seulement à l'aide d'un mot de passe, elle doit être ouverte explicitement.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-116">But if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="e7cfb-117">Nous vous conseillons de sauvegarder la clé principale dès sa création et de stocker cette sauvegarde en lieu sûr, en dehors de votre lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-117">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e7cfb-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="e7cfb-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7cfb-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e7cfb-119">Permissions</span></span>  
 <span data-ttu-id="e7cfb-120">Requiert l'autorisation CONTROL sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-120">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="Procedure"></a><span data-ttu-id="e7cfb-121">Utilisation de SQL Server Management Studio avec Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7cfb-121">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-database-master-key"></a><span data-ttu-id="e7cfb-122">Pour sauvegarder la clé principale de base de données</span><span class="sxs-lookup"><span data-stu-id="e7cfb-122">To back-up the database master key</span></span>  
  
1.  <span data-ttu-id="e7cfb-123">Dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connectez-vous à l'instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] contenant la clé principale de base de données à sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-123">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the database master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="e7cfb-124">Choisissez un mot de passe qui servira à chiffrer la clé principale de base de données sur le support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-124">Choose a password that will be used to encrypt the database master key on the backup medium.</span></span> <span data-ttu-id="e7cfb-125">Ce mot de passe est sujet à des vérifications de complexité.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-125">This password is subject to complexity checks.</span></span>  
  
3.  <span data-ttu-id="e7cfb-126">Procurez-vous un support de sauvegarde amovible pour stocker une copie de la clé sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="e7cfb-127">Identifiez un répertoire NTFS où créer la sauvegarde de la clé.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="e7cfb-128">C'est à cet emplacement que vous allez créer le fichier spécifié à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="e7cfb-129">Le répertoire doit être protégé par des listes de contrôle d'accès très restrictives.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="e7cfb-130">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7cfb-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="e7cfb-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="e7cfb-132">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key. Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;   
    GO  
    OPEN MASTER KEY DECRYPTION BY PASSWORD = 'sfj5300osdVdgwdfkli7';   
  
    BACKUP MASTER KEY TO FILE = 'c:\temp\exportedmasterkey'   
        ENCRYPTION BY PASSWORD = 'sd092735kjn$&adsg';   
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="e7cfb-133">Le chemin d'accès à la clé et le mot de passe de la clé (s'il existe) seront différents de ce qui est indiqué ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="e7cfb-134">Assurez-vous que les deux sont spécifiques à votre installation de serveur et de clé.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-134">Please make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="e7cfb-135">Copiez le fichier sur le support de sauvegarde et vérifiez la copie.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="e7cfb-136">Conservez la sauvegarde en lieu sûr, en dehors de votre lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="e7cfb-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="e7cfb-137">Pour plus d’informations, consultez [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) et [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7cfb-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
