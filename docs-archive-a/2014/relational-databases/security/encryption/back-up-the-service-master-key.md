---
title: Sauvegarder la clé principale du service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], exporting
ms.assetid: f60b917c-6408-48be-b911-f93b05796904
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: b79212040df67c22ae7e34cd380a1a1f1bd10773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709080"
---
# <a name="back-up-the-service-master-key"></a><span data-ttu-id="89a10-102">Sauvegarder la clé principale du service</span><span class="sxs-lookup"><span data-stu-id="89a10-102">Back Up the Service Master Key</span></span>
  <span data-ttu-id="89a10-103">Cette rubrique explique comment sauvegarder la clé principale du service dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89a10-103">This topic describes how to back-up the Service Master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="89a10-104">La clé principale du service représente la racine de la hiérarchie de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="89a10-104">The service master key is the root of the encryption hierarchy.</span></span> <span data-ttu-id="89a10-105">Elle doit être sauvegardée et stockée en lieu sûr, en dehors de votre lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="89a10-105">It should be backed up and stored in a secure, off-site location.</span></span> <span data-ttu-id="89a10-106">La création de cette sauvegarde doit être l'une des premières actions administratives effectuées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="89a10-106">Creating this backup should be one of the first administrative actions performed on the server.</span></span>  
  
 <span data-ttu-id="89a10-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="89a10-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="89a10-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="89a10-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="89a10-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="89a10-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="89a10-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="89a10-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="89a10-111">Pour sauvegarder la clé principale du service</span><span class="sxs-lookup"><span data-stu-id="89a10-111">To back-up the Service Master key</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="89a10-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="89a10-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="89a10-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="89a10-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="89a10-114">La clé principale doit être ouverte et, par conséquent, déchiffrée avant d'être sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="89a10-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="89a10-115">Si elle est chiffrée avec la clé principale du service, la clé principale ne doit pas être explicitement ouverte ; toutefois, si la clé principale est chiffrée uniquement avec un mot de passe, elle doit être ouverte explicitement.</span><span class="sxs-lookup"><span data-stu-id="89a10-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened; however, if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="89a10-116">Nous vous conseillons de sauvegarder la clé principale dès sa création et de stocker cette sauvegarde en lieu sûr, en dehors de votre lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="89a10-116">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="89a10-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="89a10-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="89a10-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="89a10-118">Permissions</span></span>  
 <span data-ttu-id="89a10-119">Requiert l'autorisation CONTROL sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="89a10-119">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="Procedure"></a> <span data-ttu-id="89a10-120">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89a10-120">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-service-master-key"></a><span data-ttu-id="89a10-121">Pour sauvegarder la clé principale du service</span><span class="sxs-lookup"><span data-stu-id="89a10-121">To back-up the Service Master key</span></span>  
  
1.  <span data-ttu-id="89a10-122">Dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connectez-vous à l'instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] contenant la clé principale du service à sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="89a10-122">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the service master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="89a10-123">Choisissez un mot de passe qui servira à chiffrer la clé principale du service sur le support de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="89a10-123">Choose a password that will be used to encrypt the service master key on the backup medium.</span></span> <span data-ttu-id="89a10-124">Ce mot de passe est sujet à des vérifications de complexité.</span><span class="sxs-lookup"><span data-stu-id="89a10-124">This password is subject to complexity checks.</span></span> <span data-ttu-id="89a10-125">Pour plus d'informations, consultez [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="89a10-125">For more information, see [Password Policy](../password-policy.md).</span></span>  
  
3.  <span data-ttu-id="89a10-126">Procurez-vous un support de sauvegarde amovible pour stocker une copie de la clé sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="89a10-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="89a10-127">Identifiez un répertoire NTFS où créer la sauvegarde de la clé.</span><span class="sxs-lookup"><span data-stu-id="89a10-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="89a10-128">C'est à cet emplacement que vous allez créer le fichier spécifié à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="89a10-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="89a10-129">Le répertoire doit être protégé par des listes de contrôle d'accès très restrictives.</span><span class="sxs-lookup"><span data-stu-id="89a10-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="89a10-130">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89a10-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="89a10-131">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="89a10-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="89a10-132">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="89a10-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key.  
    -- Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;  
    GO  
    BACKUP SERVICE MASTER KEY TO FILE = 'c:\temp_backups\keys\service_master_ key'   
        ENCRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="89a10-133">Le chemin d'accès à la clé et le mot de passe de la clé (s'il existe) seront différents de ce qui est indiqué ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="89a10-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="89a10-134">Vérifiez que les deux sont spécifiques à votre installation de serveur et de clé.</span><span class="sxs-lookup"><span data-stu-id="89a10-134">Make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="89a10-135">Copiez le fichier sur le support de sauvegarde et vérifiez la copie.</span><span class="sxs-lookup"><span data-stu-id="89a10-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="89a10-136">Conservez la sauvegarde en lieu sûr, en dehors de votre lieu de travail.</span><span class="sxs-lookup"><span data-stu-id="89a10-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="89a10-137">Pour plus d’informations, consultez [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) et [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="89a10-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
