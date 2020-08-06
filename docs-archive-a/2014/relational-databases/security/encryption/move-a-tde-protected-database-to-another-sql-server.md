---
title: Déplacer une base de données protégée par le chiffrement transparent des données vers un autre serveur SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, moving
- TDE, moving a database
ms.assetid: fb420903-df54-4016-bab6-49e6dfbdedc7
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b03b4d9ecf31e9953fd3e22cec5c51bbacc0c25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710528"
---
# <a name="move-a-tde-protected-database-to-another-sql-server"></a><span data-ttu-id="256d3-102">Déplacer une base de données protégée par le chiffrement transparent des données vers un autre serveur SQL Server</span><span class="sxs-lookup"><span data-stu-id="256d3-102">Move a TDE Protected Database to Another SQL Server</span></span>
  <span data-ttu-id="256d3-103">Cette rubrique explique comment protéger une base de données à l’aide du chiffrement transparent des données (TDE), puis la déplacer vers une autre instance de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l’aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="256d3-103">This topic describes how to protect a database by using transparent data encryption (TDE), and then move the database to another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="256d3-104">TDE effectue le chiffrement et le déchiffrement d’E/S en temps réel des données et des fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="256d3-104">TDE performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="256d3-105">Le chiffrement utilise une clé de chiffrement de base de données stockée dans l’enregistrement de démarrage de base de données à des fins de disponibilité lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="256d3-105">The encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="256d3-106">La clé de chiffrement de base de données est une clé symétrique sécurisée à l'aide d'un certificat stocké dans la base de données `master` du serveur ou une clé asymétrique protégée par un module de gestion de clés extensible.</span><span class="sxs-lookup"><span data-stu-id="256d3-106">The DEK is a symmetric key secured by using a certificate stored in the `master` database of the server or an asymmetric key protected by an EKM module.</span></span>  
  
 <span data-ttu-id="256d3-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="256d3-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="256d3-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="256d3-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="256d3-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="256d3-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="256d3-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="256d3-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="256d3-111">**Pour créer une base de données protégée par le chiffrement transparent des données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="256d3-111">**To create a database protected by transparent data encryption, using:**</span></span>  
  
     [<span data-ttu-id="256d3-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="256d3-112">SQL Server Management Studio</span></span>](#SSMSCreate)  
  
     [<span data-ttu-id="256d3-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="256d3-113">Transact-SQL</span></span>](#TsqlCreate)  
  
-   <span data-ttu-id="256d3-114">**Pour déplacer une base de données, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="256d3-114">**To move a database, using:**</span></span>  
  
     [<span data-ttu-id="256d3-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="256d3-115">SQL Server Management Studio</span></span>](#SSMSMove)  
  
     [<span data-ttu-id="256d3-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="256d3-116">Transact-SQL</span></span>](#TsqlMove)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="256d3-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="256d3-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="256d3-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="256d3-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="256d3-119">Lors du déplacement d'une base de données protégée par chiffrement transparent des données, vous devez également déplacer le certificat ou la clé asymétrique qui sert à ouvrir la clé DEK.</span><span class="sxs-lookup"><span data-stu-id="256d3-119">When moving a TDE protected database, you must also move the certificate or asymmetric key that is used to open the DEK.</span></span> <span data-ttu-id="256d3-120">Le certificat ou la clé asymétrique doit être installé dans la `master` base de données du serveur de destination, afin que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] puisse accéder aux fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-120">The certificate or asymmetric key must be installed in the `master` database of the destination server, so that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can access the database files.</span></span> <span data-ttu-id="256d3-121">Pour plus d’informations, consultez [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="256d3-121">For more information, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span>  
  
-   <span data-ttu-id="256d3-122">Vous devez conserver des copies du fichier de certificat et du fichier de clé privée pour permettre la récupération du certificat.</span><span class="sxs-lookup"><span data-stu-id="256d3-122">You must retain copies of both the certificate file and the private key file in order to recover the certificate.</span></span> <span data-ttu-id="256d3-123">Le mot de passe de la clé privée ne doit pas forcément être le même que le mot de passe de la clé principale de la base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-123">The password for the private key does not have to be the same as the database master key password.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="256d3-124">stocke les fichiers créés ici dans **C:\Program Files\Microsoft SQL Server\MSSQL12. MSSQLSERVER\MSSQL\DATA** par défaut.</span><span class="sxs-lookup"><span data-stu-id="256d3-124">stores the files created here in **C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA** by default.</span></span> <span data-ttu-id="256d3-125">Vos noms et emplacements de fichier peuvent être différents.</span><span class="sxs-lookup"><span data-stu-id="256d3-125">Your file names and locations might be different.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="256d3-126">Sécurité</span><span class="sxs-lookup"><span data-stu-id="256d3-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="256d3-127">Autorisations</span><span class="sxs-lookup"><span data-stu-id="256d3-127">Permissions</span></span>  
  
-   <span data-ttu-id="256d3-128">Nécessite l' `CONTROL DATABASE` autorisation sur la `master` base de données pour créer la clé principale de base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-128">Requires `CONTROL DATABASE` permission on the `master` database to create the database master key.</span></span>  
  
-   <span data-ttu-id="256d3-129">Nécessite l' `CREATE CERTIFICATE` autorisation sur la `master` base de données pour créer le certificat qui protège le Dek.</span><span class="sxs-lookup"><span data-stu-id="256d3-129">Requires `CREATE CERTIFICATE` permission on the `master` database to create the certificate that protects the DEK.</span></span>  
  
-   <span data-ttu-id="256d3-130">Requiert l'autorisation `CONTROL DATABASE` sur la base de données chiffrée et l'autorisation `VIEW DEFINITION` sur le certificat ou la clé asymétrique qui sert à chiffrer la clé de chiffrement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-130">Requires `CONTROL DATABASE` permission on the encrypted database and `VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database encryption key.</span></span>  
  
##  <a name="to-create-a-database-protected-by-transparent-data-encryption"></a><a name="SSMSProcedure"></a> <span data-ttu-id="256d3-131">Pour créer une base de données protégée par le chiffrement transparent des données</span><span class="sxs-lookup"><span data-stu-id="256d3-131">To create a database protected by transparent data encryption</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSCreate"></a> <span data-ttu-id="256d3-132">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="256d3-132">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="256d3-133">Créez une clé principale de base de données et un certificat dans la `master` base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-133">Create a database master key and certificate in the `master` database.</span></span> <span data-ttu-id="256d3-134">Pour plus d’informations, consultez **Utilisation de Transact-SQL** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="256d3-134">For more information, see **Using Transact-SQL** below.</span></span>  
  
2.  <span data-ttu-id="256d3-135">Créez une sauvegarde du certificat de serveur dans la `master` base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-135">Create a backup of the server certificate in the `master` database.</span></span> <span data-ttu-id="256d3-136">Pour plus d’informations, consultez **Utilisation de Transact-SQL** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="256d3-136">For more information, see **Using Transact-SQL** below.</span></span>  
  
3.  <span data-ttu-id="256d3-137">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le dossier **Bases de données** et sélectionnez **Nouvelle base de données**.</span><span class="sxs-lookup"><span data-stu-id="256d3-137">In Object Explorer, right-click the **Databases** folder and select **New Database**.</span></span>  
  
4.  <span data-ttu-id="256d3-138">Dans la boîte de dialogue **Nouvelle base de données** , dans la zone **Nom de la base de données** , entrez le nom de la nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-138">In the **New Database** dialog box, in the **Database name** box, enter the name of the new database.</span></span>  
  
5.  <span data-ttu-id="256d3-139">Dans la zone **Propriétaire** , entrez le nom du propriétaire de la nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-139">In the **Owner** box, enter the name of the new database's owner.</span></span> <span data-ttu-id="256d3-140">Vous pouvez également cliquer sur les points de suspension **(…)** pour ouvrir la boîte de dialogue **Sélectionner le propriétaire de la base de données**.</span><span class="sxs-lookup"><span data-stu-id="256d3-140">Alternately, click the ellipsis **(...)** to open the **Select Database Owner** dialog box.</span></span> <span data-ttu-id="256d3-141">Pour plus d'informations sur la création d'une nouvelle base de données, consultez [Create a Database](../../databases/create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="256d3-141">For more information on creating a new database, see [Create a Database](../../databases/create-a-database.md).</span></span>  
  
6.  <span data-ttu-id="256d3-142">Dans l'Explorateur d'objets, cliquez sur le signe plus pour développer le dossier **Bases de données** .</span><span class="sxs-lookup"><span data-stu-id="256d3-142">In Object Explorer, click the plus sign to expand the **Databases** folder.</span></span>  
  
7.  <span data-ttu-id="256d3-143">Cliquez avec le bouton droit sur la base de données que vous avez créée, pointez sur **Tâches**, puis sélectionnez **Gérer le chiffrement de base de données**.</span><span class="sxs-lookup"><span data-stu-id="256d3-143">Right-click the database you created, point to **Tasks**, and select **Manage Database Encryption**.</span></span>  
  
     <span data-ttu-id="256d3-144">Les options suivantes sont disponibles dans la boîte de dialogue **Gérer le chiffrement de base de données** .</span><span class="sxs-lookup"><span data-stu-id="256d3-144">The following options are available on the **Manage Database Encryption** dialog box.</span></span>  
  
     <span data-ttu-id="256d3-145">**Algorithme de chiffrement**</span><span class="sxs-lookup"><span data-stu-id="256d3-145">**Encryption Algorithm**</span></span>  
     <span data-ttu-id="256d3-146">Affiche ou définit l'algorithme à utiliser pour le chiffrement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-146">Displays or sets the algorithm to use for database encryption.</span></span> <span data-ttu-id="256d3-147">`AES128` est l'algorithme par défaut.</span><span class="sxs-lookup"><span data-stu-id="256d3-147">`AES128` is the default algorithm.</span></span> <span data-ttu-id="256d3-148">Ce champ ne peut pas être vide.</span><span class="sxs-lookup"><span data-stu-id="256d3-148">This field cannot be blank.</span></span> <span data-ttu-id="256d3-149">Pour plus d'informations sur les algorithmes de chiffrement, consultez [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="256d3-149">For more information on encryption algorithms, see [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span></span>  
  
     <span data-ttu-id="256d3-150">**Utilisez un certificat de serveur**</span><span class="sxs-lookup"><span data-stu-id="256d3-150">**Use server certificate**</span></span>  
     <span data-ttu-id="256d3-151">Définit le chiffrement à sécuriser par un certificat.</span><span class="sxs-lookup"><span data-stu-id="256d3-151">Sets the encryption to be secured by a certificate.</span></span> <span data-ttu-id="256d3-152">Sélectionnez une option dans la liste.</span><span class="sxs-lookup"><span data-stu-id="256d3-152">Select one from the list.</span></span> <span data-ttu-id="256d3-153">Si vous n'avez pas l'autorisation `VIEW DEFINITION` sur les certificats de serveur, cette liste sera vide.</span><span class="sxs-lookup"><span data-stu-id="256d3-153">If you do not have the `VIEW DEFINITION` permission on server certificates, this list will be empty.</span></span> <span data-ttu-id="256d3-154">Si une méthode de chiffrement de certificat est sélectionnée, cette valeur ne peut pas être vide.</span><span class="sxs-lookup"><span data-stu-id="256d3-154">If a certificate method of encryption is selected, this value cannot be empty.</span></span> <span data-ttu-id="256d3-155">Pour plus d'informations sur les certificats, consultez [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="256d3-155">For more information about certificates, see [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
     <span data-ttu-id="256d3-156">**Utilisez une clé asymétrique de serveur**</span><span class="sxs-lookup"><span data-stu-id="256d3-156">**Use server asymmetric key**</span></span>  
     <span data-ttu-id="256d3-157">Définit le chiffrement à sécuriser par une clé asymétrique.</span><span class="sxs-lookup"><span data-stu-id="256d3-157">Sets the encryption to be secured by an asymmetric key.</span></span> <span data-ttu-id="256d3-158">Seules les clés asymétriques disponibles sont affichées.</span><span class="sxs-lookup"><span data-stu-id="256d3-158">Only available asymmetric keys are displayed.</span></span> <span data-ttu-id="256d3-159">Seule une clé asymétrique protégée par un module EKM peut chiffrer une base de données en utilisant le chiffrement transparent de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-159">Only an asymmetric key protected by an EKM module can encrypt a database using TDE.</span></span>  
  
     <span data-ttu-id="256d3-160">**Définir le chiffrement de la base de données sur**</span><span class="sxs-lookup"><span data-stu-id="256d3-160">**Set Database Encryption On**</span></span>  
     <span data-ttu-id="256d3-161">Modifie la base de données pour activer ou désactiver le chiffrement transparent des données.</span><span class="sxs-lookup"><span data-stu-id="256d3-161">Alters the database to turn on (checked) or turn off (unchecked) TDE.</span></span>  
  
8.  <span data-ttu-id="256d3-162">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="256d3-162">When finished, click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlCreate"></a> <span data-ttu-id="256d3-163">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="256d3-163">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="256d3-164">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="256d3-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="256d3-165">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="256d3-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="256d3-166">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="256d3-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a database master key and a certificate in the master database.  
    USE master ;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    CREATE CERTIFICATE TestSQLServerCert   
    WITH SUBJECT = 'Certificate to protect TDE key'  
    GO  
    -- Create a backup of the server certificate in the master database.  
    -- The following code stores the backup of the certificate and the private key file in the default data location for this instance of SQL Server   
    -- (C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA).  
  
    BACKUP CERTIFICATE TestSQLServerCert   
    TO FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Create a database to be protected by TDE.  
    CREATE DATABASE CustRecords ;  
    GO  
    -- Switch to the new database.  
    -- Create a database encryption key, that is protected by the server certificate in the master database.   
    -- Alter the new database to encrypt the database using TDE.  
    USE CustRecords;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM = AES_128  
    ENCRYPTION BY SERVER CERTIFICATE TestSQLServerCert;  
    GO  
    ALTER DATABASE CustRecords  
    SET ENCRYPTION ON;  
    GO  
    ```  
  
 <span data-ttu-id="256d3-167">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="256d3-167">For more information, see:</span></span>  
  
-   [<span data-ttu-id="256d3-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="256d3-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="256d3-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-certificate-transact-sql)  
  
-   [<span data-ttu-id="256d3-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="256d3-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="256d3-173">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-173">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
##  <a name="to-move-a-database"></a><a name="TsqlProcedure"></a><span data-ttu-id="256d3-174">Pour déplacer une base de données</span><span class="sxs-lookup"><span data-stu-id="256d3-174">To move a database</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSMove"></a> <span data-ttu-id="256d3-175">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="256d3-175">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="256d3-176">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la base de données que vous avez chiffrée précédemment, pointez sur **Tâches** et sélectionnez **Détacher…** .</span><span class="sxs-lookup"><span data-stu-id="256d3-176">In Object Explorer, right-click the database you encrypted above, point to **Tasks** and select **Detach...**.</span></span>  
  
     <span data-ttu-id="256d3-177">Les options suivantes sont disponibles dans la boîte de dialogue **Détacher la base de données** .</span><span class="sxs-lookup"><span data-stu-id="256d3-177">The following options are available in the **Detach Database** dialog box.</span></span>  
  
     <span data-ttu-id="256d3-178">**Bases de données à détacher**</span><span class="sxs-lookup"><span data-stu-id="256d3-178">**Databases to detach**</span></span>  
     <span data-ttu-id="256d3-179">Répertorie les bases de données à détacher.</span><span class="sxs-lookup"><span data-stu-id="256d3-179">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="256d3-180">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="256d3-180">**Database Name**</span></span>  
     <span data-ttu-id="256d3-181">Spécifie le nom de la base de données à détacher.</span><span class="sxs-lookup"><span data-stu-id="256d3-181">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="256d3-182">**Supprimer les connexions**</span><span class="sxs-lookup"><span data-stu-id="256d3-182">**Drop Connections**</span></span>  
     <span data-ttu-id="256d3-183">Permet de déconnecter les connexions à la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="256d3-183">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="256d3-184">Vous ne pouvez pas détacher une base de données avec des connexions actives.</span><span class="sxs-lookup"><span data-stu-id="256d3-184">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="256d3-185">**Mettre à jour les statistiques**</span><span class="sxs-lookup"><span data-stu-id="256d3-185">**Update Statistics**</span></span>  
     <span data-ttu-id="256d3-186">Par défaut, l'opération de détachement conserve toutes les statistiques d'optimisation obsolètes avant de procéder au détachement ; pour actualiser les statistiques existantes, activez cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="256d3-186">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="256d3-187">**Conserver les catalogues de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="256d3-187">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="256d3-188">Par défaut, l'opération de détachement conserve tous les catalogues de texte intégral associés à la base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-188">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="256d3-189">Pour les supprimer, décochez la case **Conserver les catalogues de texte intégral** .</span><span class="sxs-lookup"><span data-stu-id="256d3-189">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="256d3-190">Cette option s'affiche uniquement lors de la mise à niveau d'une base de données à partir de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="256d3-190">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="256d3-191">**État**</span><span class="sxs-lookup"><span data-stu-id="256d3-191">**Status**</span></span>  
     <span data-ttu-id="256d3-192">Affiche un des états suivants : **Prêt** ou **Non prêt**.</span><span class="sxs-lookup"><span data-stu-id="256d3-192">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="256d3-193">**Message**</span><span class="sxs-lookup"><span data-stu-id="256d3-193">**Message**</span></span>  
     <span data-ttu-id="256d3-194">La colonne **Message** peut indiquer des informations sur la base de données, comme suit :</span><span class="sxs-lookup"><span data-stu-id="256d3-194">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="256d3-195">Lorsqu'une base de données est impliquée dans la réplication, l' **État** est **Non prêt** et la colonne **Message** indique **Base de données répliquée**.</span><span class="sxs-lookup"><span data-stu-id="256d3-195">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="256d3-196">Quand une base de données a une ou plusieurs connexions actives, l’**État** est **Non prêt** et la colonne **Message** indique _<nombre_de_connexions_actives>_ **Connexion(s) active(s)**  ; par exemple : **1 connexion(s) active(s)** .</span><span class="sxs-lookup"><span data-stu-id="256d3-196">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="256d3-197">Avant de détacher la base de données, vous devez déconnecter toutes les connexions actives en cliquant sur **Supprimer les connexions**.</span><span class="sxs-lookup"><span data-stu-id="256d3-197">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="256d3-198">Pour obtenir plus d'informations sur un message, cliquez sur le texte du lien hypertexte pour ouvrir le Moniteur d'activité.</span><span class="sxs-lookup"><span data-stu-id="256d3-198">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
2.  <span data-ttu-id="256d3-199">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="256d3-199">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="256d3-200">À l'aide de l'Explorateur Windows, déplacez ou copiez les fichiers de base de données depuis le serveur source vers le même emplacement sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="256d3-200">Using Windows Explorer, move or copy the database files from the source server to the same location on the destination server.</span></span>  
  
4.  <span data-ttu-id="256d3-201">À l'aide de l'Explorateur Windows, déplacez ou copiez la sauvegarde du certificat de serveur et le fichier de clé privée depuis le serveur source vers le même emplacement sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="256d3-201">Using Windows Explorer, move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.</span></span>  
  
5.  <span data-ttu-id="256d3-202">Créez une clé principale de base de données sur l'instance de destination de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="256d3-202">Create a database master key on the destination instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="256d3-203">Pour plus d’informations, consultez **Utilisation de Transact-SQL** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="256d3-203">For more information, see **Using Transact-SQL** below.</span></span>  
  
6.  <span data-ttu-id="256d3-204">Recréez le certificat de serveur à l'aide du fichier de sauvegarde du certificat de serveur d'origine.</span><span class="sxs-lookup"><span data-stu-id="256d3-204">Recreate the server certificate by using the original server certificate backup file.</span></span> <span data-ttu-id="256d3-205">Pour plus d’informations, consultez **Utilisation de Transact-SQL** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="256d3-205">For more information, see **Using Transact-SQL** below.</span></span>  
  
7.  <span data-ttu-id="256d3-206">Dans l’Explorateur d’objets, dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], cliquez avec le bouton droit sur le dossier **Bases de données** et sélectionnez **Attacher…** .</span><span class="sxs-lookup"><span data-stu-id="256d3-206">In Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], right-click the **Databases** folder and select **Attach...**.</span></span>  
  
8.  <span data-ttu-id="256d3-207">Dans la boîte de dialogue **Attacher des bases de données** , sous **Bases de données à attacher**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="256d3-207">In the **Attach Databases** dialog box, under **Databases to attach**, click **Add**.</span></span>  
  
9. <span data-ttu-id="256d3-208">Dans la boîte de dialogue **Rechercher les fichiers de base de données-**_SERVER_NAME_ , sélectionnez le fichier de base de données à attacher au nouveau serveur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="256d3-208">In the **Locate Database Files -**_server_name_ dialog box, select the database file to attach to the new server and click **OK**.</span></span>  
  
     <span data-ttu-id="256d3-209">Les options suivantes sont disponibles dans la boîte de dialogue **Attacher des bases de données** .</span><span class="sxs-lookup"><span data-stu-id="256d3-209">The following options are available in the **Attach Databases** dialog box.</span></span>  
  
     <span data-ttu-id="256d3-210">**Bases de données à attacher**</span><span class="sxs-lookup"><span data-stu-id="256d3-210">**Databases to attach**</span></span>  
     <span data-ttu-id="256d3-211">Affiche des informations sur les bases de données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="256d3-211">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="256d3-212">Affiche une icône indiquant l'état de l'opération d'attachement.</span><span class="sxs-lookup"><span data-stu-id="256d3-212">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="256d3-213">Les icônes possibles sont décrites dans la section **État** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="256d3-213">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="256d3-214">**Emplacement du fichier MDF**</span><span class="sxs-lookup"><span data-stu-id="256d3-214">**MDF File Location**</span></span>  
     <span data-ttu-id="256d3-215">Affiche le chemin d'accès et le nom du fichier MDF sélectionné.</span><span class="sxs-lookup"><span data-stu-id="256d3-215">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="256d3-216">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="256d3-216">**Database Name**</span></span>  
     <span data-ttu-id="256d3-217">Affiche le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-217">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="256d3-218">**Attacher en tant que**</span><span class="sxs-lookup"><span data-stu-id="256d3-218">**Attach As**</span></span>  
     <span data-ttu-id="256d3-219">Permet de spécifier éventuellement un autre nom sous lequel la base de données doit être attachée.</span><span class="sxs-lookup"><span data-stu-id="256d3-219">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="256d3-220">**Propriétaire**</span><span class="sxs-lookup"><span data-stu-id="256d3-220">**Owner**</span></span>  
     <span data-ttu-id="256d3-221">Fournit une liste déroulante des propriétaires de bases de données possibles dans laquelle vous pouvez sélectionner un autre propriétaire.</span><span class="sxs-lookup"><span data-stu-id="256d3-221">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="256d3-222">**État**</span><span class="sxs-lookup"><span data-stu-id="256d3-222">**Status**</span></span>  
     <span data-ttu-id="256d3-223">Affiche l'état de la base de données conformément au tableau ci-après.</span><span class="sxs-lookup"><span data-stu-id="256d3-223">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="256d3-224">Icône</span><span class="sxs-lookup"><span data-stu-id="256d3-224">Icon</span></span>|<span data-ttu-id="256d3-225">Texte d'état</span><span class="sxs-lookup"><span data-stu-id="256d3-225">Status text</span></span>|<span data-ttu-id="256d3-226">Description</span><span class="sxs-lookup"><span data-stu-id="256d3-226">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="256d3-227">(Aucune icône)</span><span class="sxs-lookup"><span data-stu-id="256d3-227">(No icon)</span></span>|<span data-ttu-id="256d3-228">(Aucun texte)</span><span class="sxs-lookup"><span data-stu-id="256d3-228">(No text)</span></span>|<span data-ttu-id="256d3-229">L'opération d'attachement n'a pas démarré ou est peut-être en attente pour cet objet.</span><span class="sxs-lookup"><span data-stu-id="256d3-229">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="256d3-230">Il s'agit de la valeur par défaut lorsque la boîte de dialogue est ouverte.</span><span class="sxs-lookup"><span data-stu-id="256d3-230">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="256d3-231">Triangle vert dirigé vers la droite</span><span class="sxs-lookup"><span data-stu-id="256d3-231">Green, right-pointing triangle</span></span>|<span data-ttu-id="256d3-232">En cours</span><span class="sxs-lookup"><span data-stu-id="256d3-232">In progress</span></span>|<span data-ttu-id="256d3-233">L'opération d'attachement a démarré, mais n'est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="256d3-233">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="256d3-234">Coche verte</span><span class="sxs-lookup"><span data-stu-id="256d3-234">Green check mark</span></span>|<span data-ttu-id="256d3-235">Succès</span><span class="sxs-lookup"><span data-stu-id="256d3-235">Success</span></span>|<span data-ttu-id="256d3-236">L'attachement de l'objet a réussi.</span><span class="sxs-lookup"><span data-stu-id="256d3-236">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="256d3-237">Cercle rouge contenant une croix blanche</span><span class="sxs-lookup"><span data-stu-id="256d3-237">Red circle containing a white cross</span></span>|<span data-ttu-id="256d3-238">Error</span><span class="sxs-lookup"><span data-stu-id="256d3-238">Error</span></span>|<span data-ttu-id="256d3-239">L'opération d'attachement a rencontré une erreur et ne s'est pas terminée correctement.</span><span class="sxs-lookup"><span data-stu-id="256d3-239">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="256d3-240">Cercle contenant deux quartiers noirs (à gauche et à droite) et deux quartiers blancs (en haut et en bas)</span><span class="sxs-lookup"><span data-stu-id="256d3-240">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="256d3-241">Arrêté</span><span class="sxs-lookup"><span data-stu-id="256d3-241">Stopped</span></span>|<span data-ttu-id="256d3-242">L'opération d'attachement n'a pas réussi, car l'utilisateur l'a interrompue.</span><span class="sxs-lookup"><span data-stu-id="256d3-242">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="256d3-243">Cercle contenant une flèche courbe pointant dans le sens inverse des aiguilles d'une montre</span><span class="sxs-lookup"><span data-stu-id="256d3-243">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="256d3-244">Restauré</span><span class="sxs-lookup"><span data-stu-id="256d3-244">Rolled Back</span></span>|<span data-ttu-id="256d3-245">L'opération d'attachement a réussi, mais a été restaurée en raison d'une erreur lors de l'attachement d'un autre objet.</span><span class="sxs-lookup"><span data-stu-id="256d3-245">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="256d3-246">**Message**</span><span class="sxs-lookup"><span data-stu-id="256d3-246">**Message**</span></span>  
     <span data-ttu-id="256d3-247">Affiche un message vierge ou un lien hypertexte « Fichier introuvable ».</span><span class="sxs-lookup"><span data-stu-id="256d3-247">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="256d3-248">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="256d3-248">**Add**</span></span>  
     <span data-ttu-id="256d3-249">Permet de rechercher les principaux fichiers de base de données nécessaires.</span><span class="sxs-lookup"><span data-stu-id="256d3-249">Find the necessary main database files.</span></span> <span data-ttu-id="256d3-250">Lorsque l'utilisateur sélectionne un fichier .mdf, les informations applicables sont automatiquement remplies dans les champs respectifs de la grille **Bases de données à attacher** .</span><span class="sxs-lookup"><span data-stu-id="256d3-250">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="256d3-251">**Remove**</span><span class="sxs-lookup"><span data-stu-id="256d3-251">**Remove**</span></span>  
     <span data-ttu-id="256d3-252">Supprime le fichier sélectionné de la grille **Bases de données à attacher** .</span><span class="sxs-lookup"><span data-stu-id="256d3-252">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="256d3-253">**Détails de la base de données "** _<nom_base_de_données>_ **"**</span><span class="sxs-lookup"><span data-stu-id="256d3-253">**"** _<database_name>_ **" database details**</span></span>  
     <span data-ttu-id="256d3-254">Affiche le nom des fichiers à attacher.</span><span class="sxs-lookup"><span data-stu-id="256d3-254">Displays the names of the files to be attached.</span></span> <span data-ttu-id="256d3-255">Pour vérifier ou changer le nom du chemin d’accès d’un fichier, cliquez sur le bouton **Parcourir** ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="256d3-255">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="256d3-256">Si un fichier n'existe pas, la colonne **Message** affiche « Introuvable ».</span><span class="sxs-lookup"><span data-stu-id="256d3-256">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="256d3-257">Si un fichier journal est introuvable, cela signifie qu'il se trouve dans un autre répertoire ou qu'il a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="256d3-257">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="256d3-258">Vous devez mettre à jour le chemin d'accès du fichier dans la grille **Détails de la base de données** pour désigner l'emplacement correct ou supprimer le fichier journal de la grille.</span><span class="sxs-lookup"><span data-stu-id="256d3-258">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="256d3-259">Si un fichier de données .ndf est introuvable, vous devez mettre à jour son chemin d'accès dans la grille pour désigner l'emplacement correct.</span><span class="sxs-lookup"><span data-stu-id="256d3-259">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="256d3-260">**Nom du fichier d'origine**</span><span class="sxs-lookup"><span data-stu-id="256d3-260">**Original File Name**</span></span>  
     <span data-ttu-id="256d3-261">Affiche le nom du fichier attaché appartenant à la base de données.</span><span class="sxs-lookup"><span data-stu-id="256d3-261">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="256d3-262">**Type de fichier**</span><span class="sxs-lookup"><span data-stu-id="256d3-262">**File Type**</span></span>  
     <span data-ttu-id="256d3-263">Indique le type du fichier, **Données** ou **Journal**.</span><span class="sxs-lookup"><span data-stu-id="256d3-263">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="256d3-264">**Chemin d'accès au fichier actuel**</span><span class="sxs-lookup"><span data-stu-id="256d3-264">**Current File Path**</span></span>  
     <span data-ttu-id="256d3-265">Affiche le chemin d'accès au fichier de base de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="256d3-265">Displays the path to the selected database file.</span></span> <span data-ttu-id="256d3-266">Le chemin d'accès peut être modifié manuellement.</span><span class="sxs-lookup"><span data-stu-id="256d3-266">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="256d3-267">**Message**</span><span class="sxs-lookup"><span data-stu-id="256d3-267">**Message**</span></span>  
     <span data-ttu-id="256d3-268">Affiche un message vierge ou un lien hypertexte «**Fichier introuvable**».</span><span class="sxs-lookup"><span data-stu-id="256d3-268">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlMove"></a> <span data-ttu-id="256d3-269">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="256d3-269">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="256d3-270">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="256d3-270">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="256d3-271">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="256d3-271">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="256d3-272">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="256d3-272">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Detach the TDE protected database from the source server.   
    USE master ;  
    GO  
    EXEC master.dbo.sp_detach_db @dbname = N'CustRecords';  
    GO  
    -- Move or copy the database files from the source server to the same location on the destination server.   
    -- Move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.   
    -- Create a database master key on the destination instance of SQL Server.   
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    -- Recreate the server certificate by using the original server certificate backup file.   
    -- The password must be the same as the password that was used when the backup was created.  
  
    CREATE CERTIFICATE TestSQLServerCert   
    FROM FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        DECRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Attach the database that is being moved.   
    -- The path of the database files must be the location where you have stored the database files.  
    CREATE DATABASE [CustRecords] ON   
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords.mdf' ),  
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords_log.LDF' )  
    FOR ATTACH ;  
    GO  
    ```  
  
 <span data-ttu-id="256d3-273">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="256d3-273">For more information, see:</span></span>  
  
-   [<span data-ttu-id="256d3-274">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-274">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
-   [<span data-ttu-id="256d3-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="256d3-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="256d3-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="256d3-278">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="256d3-278">See Also</span></span>  
 [<span data-ttu-id="256d3-279">Attacher et détacher une base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="256d3-279">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../databases/database-detach-and-attach-sql-server.md)  
  
  
