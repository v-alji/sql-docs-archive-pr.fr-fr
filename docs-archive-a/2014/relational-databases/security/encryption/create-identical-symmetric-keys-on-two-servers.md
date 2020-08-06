---
title: Créer des clés symétriques identiques sur deux serveurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- symmetric keys [SQL Server], creating
ms.assetid: a13d0b21-a43b-43c0-9c22-7ba8f3d15e80
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 38eaccffff89b0be7e59f628fcfb9b6e772a02b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709079"
---
# <a name="create-identical-symmetric-keys-on-two-servers"></a><span data-ttu-id="6a15a-102">Créer des clés symétriques identiques sur deux serveurs</span><span class="sxs-lookup"><span data-stu-id="6a15a-102">Create Identical Symmetric Keys on Two Servers</span></span>
  <span data-ttu-id="6a15a-103">Cette rubrique décrit comment créer des clés symétriques identiques sur deux serveurs différents dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a15a-103">This topic describes how to create identical symmetric keys on two different servers in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6a15a-104">Pour pouvoir déchiffrer du texte chiffré, vous devez posséder la clé qui a été utilisée pour le chiffrer.</span><span class="sxs-lookup"><span data-stu-id="6a15a-104">In order to decrypt ciphertext, you need the key that was used to encrypt it.</span></span> <span data-ttu-id="6a15a-105">Quand le chiffrement et le déchiffrement interviennent dans une seule base de données, la clé est stockée dans la base de données et demeure disponible, en fonction des autorisations, pour le chiffrement et le déchiffrement.</span><span class="sxs-lookup"><span data-stu-id="6a15a-105">When both encryption and decryption occur in a single database, the key is stored in the database and it is available, depending on permissions, for both encryption and decryption.</span></span> <span data-ttu-id="6a15a-106">Cependant, lorsque le chiffrement et le déchiffrement se produisent dans des bases de données distinctes ou sur des serveurs séparés, la clé stockée dans une base de données ne peut pas être utilisée dans l'autre base de données.</span><span class="sxs-lookup"><span data-stu-id="6a15a-106">But when encryption and decryption occur in separate databases or on separate servers, the key stored in one database is not available for use on the second database</span></span>  
  
 <span data-ttu-id="6a15a-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="6a15a-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6a15a-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="6a15a-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6a15a-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="6a15a-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6a15a-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6a15a-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="6a15a-111">Pour créer des clés symétriques identiques sur deux serveurs différents, à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6a15a-111">To create identical symmetric keys on two different servers, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6a15a-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="6a15a-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6a15a-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="6a15a-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6a15a-114">Lorsqu'une clé symétrique est créée, elle doit être chiffrée à l'aide de l'un des éléments suivants au moins : certificat, mot de passe, clé symétrique, clé asymétrique ou PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="6a15a-114">When a symmetric key is created, the symmetric key must be encrypted by using at least one of the following: certificate, password, symmetric key, asymmetric key, or PROVIDER.</span></span> <span data-ttu-id="6a15a-115">La clé peut être soumise à plusieurs chiffrements de chaque type.</span><span class="sxs-lookup"><span data-stu-id="6a15a-115">The key can have more than one encryption of each type.</span></span> <span data-ttu-id="6a15a-116">En d'autres termes, une clé symétrique unique peut être chiffrée à l'aide de plusieurs certificats, mots de passe, clés symétriques et clés asymétriques à la fois.</span><span class="sxs-lookup"><span data-stu-id="6a15a-116">In other words, a single symmetric key can be encrypted by using multiple certificates, passwords, symmetric keys, and asymmetric keys at the same time.</span></span>  
  
-   <span data-ttu-id="6a15a-117">Lorsqu'une clé symétrique est chiffrée à l'aide d'un mot de passe à la place de la clé publique de la clé principale de base de données, l'algorithme de chiffrement TRIPLE_DES est utilisé.</span><span class="sxs-lookup"><span data-stu-id="6a15a-117">When a symmetric key is encrypted with a password instead of the public key of the database master key, the TRIPLE DES encryption algorithm is used.</span></span> <span data-ttu-id="6a15a-118">Pour cette raison, les clés créées à l'aide d'un algorithme de chiffrement renforcé, tel qu'AES, sont elles-mêmes sécurisées par un algorithme plus faible.</span><span class="sxs-lookup"><span data-stu-id="6a15a-118">Because of this, keys that are created with a strong encryption algorithm, such as AES, are themselves secured by a weaker algorithm.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6a15a-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6a15a-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6a15a-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6a15a-120">Permissions</span></span>  
 <span data-ttu-id="6a15a-121">Requiert l'autorisation ALTER ANY SYMMETRIC KEY sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="6a15a-121">Requires ALTER ANY SYMMETRIC KEY permission on the database.</span></span> <span data-ttu-id="6a15a-122">Si la clause AUTHORIZATION est spécifiée, l'autorisation IMPERSONATE sur l'utilisateur de base de données ou l'autorisation ALTER sur le rôle d'application est requise.</span><span class="sxs-lookup"><span data-stu-id="6a15a-122">If AUTHORIZATION is specified, requires IMPERSONATE permission on the database user or ALTER permission on the application role.</span></span> <span data-ttu-id="6a15a-123">Si le chiffrement s'effectue par certificat ou clé asymétrique, l'autorisation VIEW DEFINITION est requise sur le certificat ou la clé asymétrique.</span><span class="sxs-lookup"><span data-stu-id="6a15a-123">If encryption is by certificate or asymmetric key, requires VIEW DEFINITION permission on the certificate or asymmetric key.</span></span> <span data-ttu-id="6a15a-124">Les connexions Windows, les connexions [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et les rôles d'application sont les seuls à pouvoir posséder des clés symétriques.</span><span class="sxs-lookup"><span data-stu-id="6a15a-124">Only Windows logins, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins, and application roles can own symmetric keys.</span></span> <span data-ttu-id="6a15a-125">Les groupes et les rôles ne peuvent pas posséder de clés symétriques.</span><span class="sxs-lookup"><span data-stu-id="6a15a-125">Groups and roles cannot own symmetric keys.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6a15a-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6a15a-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-identical-symmetric-keys-on-two-different-servers"></a><span data-ttu-id="6a15a-127">Pour créer des clés symétriques identiques sur deux serveurs différents</span><span class="sxs-lookup"><span data-stu-id="6a15a-127">To create identical symmetric keys on two different servers</span></span>  
  
1.  <span data-ttu-id="6a15a-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a15a-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6a15a-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="6a15a-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6a15a-130">Créez une clé en exécutant les instructions CREATE MASTER KEY, CREATE CERTIFICATE et CREATE SYMMETRIC KEY suivantes.</span><span class="sxs-lookup"><span data-stu-id="6a15a-130">Create a key by running the following CREATE MASTER KEY, CREATE CERTIFICATE, and CREATE SYMMETRIC KEY statements.</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'My p@55w0Rd';  
    GO  
    CREATE CERTIFICATE [cert_keyProtection] WITH SUBJECT = 'Key Protection';  
    GO  
    CREATE SYMMETRIC KEY [key_DataShare] WITH  
        KEY_SOURCE = 'My key generation bits. This is a shared secret!',  
        ALGORITHM = AES_256,   
        IDENTITY_VALUE = 'Key Identity generation bits. Also a shared secret'  
        ENCRYPTION BY CERTIFICATE [cert_keyProtection];  
    GO  
    ```  
  
4.  <span data-ttu-id="6a15a-131">Connectez-vous à une instance de serveur distincte, ouvrez une fenêtre de requête différente et exécutez les instructions SQL ci-dessus pour créer la même clé sur le deuxième serveur.</span><span class="sxs-lookup"><span data-stu-id="6a15a-131">Connect to a separate server instance, open a different Query Window, and run the SQL statements above to create the same key on the second server.</span></span>  
  
5.  <span data-ttu-id="6a15a-132">Testez les clés en exécutant d'abord les instructions OPEN SYMMETRIC KEY et SELECT ci-dessous sur le premier serveur.</span><span class="sxs-lookup"><span data-stu-id="6a15a-132">Test the keys by first running the OPEN SYMMETRIC KEY statement and the SELECT statement below on the first server.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    SELECT encryptbykey(key_guid('key_DataShare'), 'MyData' )  
    GO  
    -- For example, the output might look like this: 0x2152F8DA8A500A9EDC2FAE26D15C302DA70D25563DAE7D5D1102E3056CE9EF95CA3E7289F7F4D0523ED0376B155FE9C3  
    ```  
  
6.  <span data-ttu-id="6a15a-133">Sur le second serveur, collez le résultat de l'instruction SELECT précédente dans le code suivant comme valeur de `@blob` et exécutez le code suivant pour vérifier que la clé dupliquée peut déchiffrer le texte chiffré.</span><span class="sxs-lookup"><span data-stu-id="6a15a-133">On the second server, paste the result of the previous SELECT statement into the following code as the value of `@blob` and run the following code to verify that the duplicate key can decrypt the ciphertext.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    DECLARE @blob varbinary(8000);  
    SET @blob = SELECT CONVERT(varchar(8000), decryptbykey(@blob));  
    GO  
    ```  
  
7.  <span data-ttu-id="6a15a-134">Fermez les clés symétriques sur les deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="6a15a-134">Close the symmetric key on both servers.</span></span>  
  
    ```  
    CLOSE SYMMETRIC KEY [key_DataShare];  
    GO  
    ```  
  
 <span data-ttu-id="6a15a-135">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6a15a-135">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="6a15a-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6a15a-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="6a15a-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6a15a-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="6a15a-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6a15a-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)  
  
-   [<span data-ttu-id="6a15a-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6a15a-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
  
-   [<span data-ttu-id="6a15a-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6a15a-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/decryptbykey-transact-sql)  
  
-   [<span data-ttu-id="6a15a-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6a15a-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/open-symmetric-key-transact-sql)  
  
  
