---
title: Répliquer des données dans des colonnes chiffrées (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], replicating data
- encryption [SQL Server replication]
- publishing [SQL Server replication], encrypted columns
ms.assetid: d1f8f586-e5a3-4a71-9391-11198d42bfa3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e1528d81faa352fdcdf37abe9ad93fda190445c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701039"
---
# <a name="replicate-data-in-encrypted-columns-sql-server-management-studio"></a><span data-ttu-id="9a6f2-102">Répliquer des données dans des colonnes chiffrées (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9a6f2-102">Replicate Data in Encrypted Columns (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9a6f2-103">La réplication permet de publier des données de colonnes chiffrées.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-103">Replication enables you to publish encrypted column data.</span></span> <span data-ttu-id="9a6f2-104">Pour déchiffrer et exploiter ces données sur l'Abonné, la clé employée pour chiffrer les données sur le serveur de publication doit également être présente sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-104">To decrypt and use this data at the Subscriber, the key that was used to encrypt the data at the Publisher must also be present on the Subscriber.</span></span> <span data-ttu-id="9a6f2-105">La réplication n'offre pas un mécanisme sécurisé de transport des clés de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-105">Replication does not provide a secure mechanism to transport encryption keys.</span></span> <span data-ttu-id="9a6f2-106">Vous devez manuellement recréer la clé de chiffrement sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-106">You must manually re-create the encryption key at the Subscriber.</span></span> <span data-ttu-id="9a6f2-107">Cette rubrique explique comment chiffrer une colonne sur le serveur de publication et vous assurer que la clé de chiffrement est disponible au niveau de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-107">This topic shows you how to encrypt a column at the Publisher and make sure that the encryption key is available at the Subscriber.</span></span>  
  
 <span data-ttu-id="9a6f2-108">Les étapes de base sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a6f2-108">The basic steps are as follows:</span></span>  
  
1.  <span data-ttu-id="9a6f2-109">Créez la clé symétrique sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-109">Create the symmetric key at the Publisher.</span></span>  
  
2.  <span data-ttu-id="9a6f2-110">Chiffrez les données de la colonne avec la clé symétrique.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-110">Encrypt column data with the symmetric key.</span></span>  
  
3.  <span data-ttu-id="9a6f2-111">Publiez la table avec la colonne chiffrée.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-111">Publish the table with the encrypted column.</span></span>  
  
4.  <span data-ttu-id="9a6f2-112">Abonnez-vous à la publication.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-112">Subscribe to the publication.</span></span>  
  
5.  <span data-ttu-id="9a6f2-113">Initialisez l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-113">Initialize the subscription.</span></span>  
  
6.  <span data-ttu-id="9a6f2-114">Recréez la clé symétrique sur l'Abonné en utilisant les mêmes valeurs ALGORITHM, KEY_SOURCE et IDENTITY_VALUE qu'à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-114">Recreate the symmetric key at the Subscriber using same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span>  
  
7.  <span data-ttu-id="9a6f2-115">Accédez aux données chiffrées de la colonne.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-115">Access the encrypted column data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a6f2-116">Il est préférable que vous utilisiez une clé symétrique pour chiffrer les données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-116">You should use a symmetric key to encrypt column data.</span></span> <span data-ttu-id="9a6f2-117">La clé symétrique elle-même peut être sécurisée selon différents moyens sur le serveur de publication et sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-117">The symmetric key itself can be secured by different means at the Publisher and Subscriber.</span></span>  
  
### <a name="to-create-and-replicate-encrypted-column-data"></a><span data-ttu-id="9a6f2-118">Pour créer et répliquer les données chiffrées de la colonne</span><span class="sxs-lookup"><span data-stu-id="9a6f2-118">To create and replicate encrypted column data</span></span>  
  
1.  <span data-ttu-id="9a6f2-119">Sur le serveur de publication, exécutez [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9a6f2-119">At the Publisher, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9a6f2-120">La valeur KEY_SOURCE est un ensemble de données précieuses qu'il est possible d'utiliser pour recréer la clé symétrique et déchiffrer des données.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-120">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="9a6f2-121">La valeur KEY_SOURCE doit toujours être stockée et transportée de manière sécurisée.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-121">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
2.  <span data-ttu-id="9a6f2-122">Exécutez [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) pour ouvrir la nouvelle clé.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-122">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
3.  <span data-ttu-id="9a6f2-123">Utilisez la fonction [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) pour chiffrer les données de la colonne sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-123">Use the [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) function to encrypt column data at the Publisher.</span></span>  
  
4.  <span data-ttu-id="9a6f2-124">Exécutez [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) pour fermer la clé.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-124">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
5.  <span data-ttu-id="9a6f2-125">Publiez la table contenant la colonne chiffrée.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-125">Publish the table that contains the encrypted column.</span></span> <span data-ttu-id="9a6f2-126">Pour plus d’informations, voir [Create a Publication](../publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="9a6f2-126">For more information, see [Create a Publication](../publish/create-a-publication.md).</span></span>  
  
6.  <span data-ttu-id="9a6f2-127">Abonnez-vous à la publication.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-127">Subscribe to the publication.</span></span> <span data-ttu-id="9a6f2-128">Pour plus d’informations, consultez [Créer un abonnement par extraction de données (pull)](../create-a-pull-subscription.md) ou [Créer un abonnement par émission (push)](../create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="9a6f2-128">For more information, see [Create a Pull Subscription](../create-a-pull-subscription.md) or [Create a Push Subscription](../create-a-push-subscription.md).</span></span>  
  
7.  <span data-ttu-id="9a6f2-129">Initialisez l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-129">Initialize the subscription.</span></span> <span data-ttu-id="9a6f2-130">Pour plus d’informations, voir [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="9a6f2-130">For more information, see [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span></span>  
  
8.  <span data-ttu-id="9a6f2-131">Sur l'abonné, exécutez [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) en utilisant les mêmes valeurs pour ALGORITHM, KEY_SOURCE et IDENTITY_VALUE qu'à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-131">At the Subscriber, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span> <span data-ttu-id="9a6f2-132">Vous pouvez spécifier une valeur différente pour la clause ENCRYPTION BY.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-132">You can specify a different value for ENCRYPTION BY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9a6f2-133">La valeur KEY_SOURCE est un ensemble de données précieuses qu'il est possible d'utiliser pour recréer la clé symétrique et déchiffrer des données.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-133">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="9a6f2-134">La valeur KEY_SOURCE doit toujours être stockée et transportée de manière sécurisée.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-134">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
9. <span data-ttu-id="9a6f2-135">Exécutez [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) pour ouvrir la nouvelle clé.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-135">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
10. <span data-ttu-id="9a6f2-136">Utilisez la fonction [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) pour déchiffrer les données répliquées sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-136">Use the [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) function to decrypt replicated data at the Subscriber.</span></span>  
  
11. <span data-ttu-id="9a6f2-137">Exécutez [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) pour fermer la clé.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-137">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a6f2-138">Exemple</span><span class="sxs-lookup"><span data-stu-id="9a6f2-138">Example</span></span>  
 <span data-ttu-id="9a6f2-139">Cet exemple crée une clé symétrique, un certificat servant à sécuriser la clé symétrique et une clé principale.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-139">This example creates a symmetric key, a certificate that is used to help secure the symmetric key, and a master key.</span></span> <span data-ttu-id="9a6f2-140">Ces clés sont créées dans la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-140">These keys are created in the publication database.</span></span> <span data-ttu-id="9a6f2-141">Elles sont ensuite utilisées pour créer une colonne chiffrée (EncryptedCreditCardApprovalCode) dans la table `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="9a6f2-141">They are then used to create an encrypted column (EncryptedCreditCardApprovalCode) in the `SalesOrderHeader` table.</span></span> <span data-ttu-id="9a6f2-142">Cette colonne est publiée dans la publication AdvWorksSalesOrdersMerge au lieu de la colonne non chiffrée CreditCardApprovalCode.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-142">This column is published in the AdvWorksSalesOrdersMerge publication instead of the unencrypted CreditCardApprovalCode column.</span></span> <span data-ttu-id="9a6f2-143">Lorsque c'est possible, demande aux utilisateurs de fournir les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-143">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="9a6f2-144">Si vous devez enregistrer les informations d'identification dans un fichier de script, vous devez sécuriser le fichier pour empêcher un accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-144">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_PublishEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/publishencryptedcolumn.sql#sp_publishencryptedcolumn)]  
  
 [!code-sql[HowTo#sp_AddMergeArticle](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepub.sql#sp_addmergearticle)]  
  
## <a name="example"></a><span data-ttu-id="9a6f2-145">Exemple</span><span class="sxs-lookup"><span data-stu-id="9a6f2-145">Example</span></span>  
 <span data-ttu-id="9a6f2-146">Cet exemple recrée la même clé symétrique dans la base de données d'abonnement en utilisant les mêmes valeurs ALGORITHM, KEY_SOURCE et IDENTITY_VALUE que dans le premier exemple.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-146">This example recreates the same symmetric key in the subscription database using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE from the first example.</span></span> <span data-ttu-id="9a6f2-147">Cet exemple part du principe que vous avez déjà initialisé un abonnement dans la publication AdvWorksSalesOrdersMerge dans le but de répliquer la colonne chiffrée.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-147">This example assumes that you have already initialized a subscription to the AdvWorksSalesOrdersMerge publication to replicate the encrypted column.</span></span> <span data-ttu-id="9a6f2-148">Lorsque c'est possible, demande aux utilisateurs de fournir les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-148">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="9a6f2-149">Si vous devez stocker des informations d'identification dans un fichier de script, vous devez sécuriser le fichier pour empêcher tout accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="9a6f2-149">If you must store credentials in a script file, you must secure the file during storage and transport to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_SubscriberEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/subscriberencryptedcolumn.sql#sp_subscriberencryptedcolumn)]  
  
## <a name="see-also"></a><span data-ttu-id="9a6f2-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a6f2-150">See Also</span></span>  
 <span data-ttu-id="9a6f2-151">[Sécurité Réplication SQL Server](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="9a6f2-151">[SQL Server Replication Security](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="9a6f2-152">Créer des clés symétriques identiques sur deux serveurs</span><span class="sxs-lookup"><span data-stu-id="9a6f2-152">Create Identical Symmetric Keys on Two Servers</span></span>](../../security/encryption/create-identical-symmetric-keys-on-two-servers.md)  
  
  
