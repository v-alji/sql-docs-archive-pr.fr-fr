---
title: Créer un point de terminaison de mise en miroir de bases de données pour l’authentification Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: baf1a4b1-6790-4275-b261-490bca33bdb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5558bc5684f2eb9053c935543db0c05d6225daf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603024"
---
# <a name="create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql"></a><span data-ttu-id="bdf75-102">Créer un point de terminaison de mise en miroir de bases de données pour l'authentification Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bdf75-102">Create a Database Mirroring Endpoint for Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="bdf75-103">Cette rubrique explique comment créer un point de terminaison de mise en miroir de bases de données qui utilise l'authentification Windows dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdf75-103">This topic describes how to create a database mirroring endpoint that uses Windows Authentication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bdf75-104">Pour prendre en charge la mise en miroir de bases de données ou [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] , chaque instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nécessite un point de terminaison de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="bdf75-104">To support database mirroring or [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires a database mirroring endpoint.</span></span> <span data-ttu-id="bdf75-105">Une instance de serveur ne peut disposer que d'un seul point de terminaison de mise en miroir de bases de données, lequel possède un port unique.</span><span class="sxs-lookup"><span data-stu-id="bdf75-105">A server instance can have only one database mirroring endpoint, which has a single port.</span></span> <span data-ttu-id="bdf75-106">Un point de terminaison de mise en miroir de bases de données peut utiliser n'importe quel point disponible sur le système local lors de la création du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="bdf75-106">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="bdf75-107">Toutes les sessions de mise en miroir des bases de données sur une instance de serveur écoutent ce port, et toutes les connexions entrantes pour la mise en miroir des bases de données utilisent ce port.</span><span class="sxs-lookup"><span data-stu-id="bdf75-107">All database mirroring sessions on a server instance listen on that port, and all incoming connections for database mirroring use that port.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bdf75-108">Si un point de terminaison de mise en miroir de bases de données existe et est déjà utilisé, nous vous recommandons de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="bdf75-108">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint.</span></span> <span data-ttu-id="bdf75-109">La suppression d'un point de terminaison en cours d'utilisation interrompt les sessions existantes.</span><span class="sxs-lookup"><span data-stu-id="bdf75-109">Dropping an in-use endpoint disrupts existing sessions.</span></span>  
  
 <span data-ttu-id="bdf75-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="bdf75-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bdf75-111">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="bdf75-111">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="bdf75-112">**Pour créer un point de terminaison de mise en miroir de bases de données à l’aide de**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="bdf75-112">**To create a database mirroring endpoint, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bdf75-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="bdf75-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bdf75-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bdf75-114">Security</span></span>  
 <span data-ttu-id="bdf75-115">Les méthodes d'authentification et de chiffrement d'instance de serveur sont établies par l'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="bdf75-115">The authentication and encryption methods of the server instance are established by the system administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bdf75-116">L'algorithme RC4 est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="bdf75-116">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="bdf75-117">Nous vous recommandons d'utiliser AES.</span><span class="sxs-lookup"><span data-stu-id="bdf75-117">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bdf75-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="bdf75-118">Permissions</span></span>  
 <span data-ttu-id="bdf75-119">Requiert l'autorisation CREATE ENDPOINT ou l'appartenance au rôle serveur fixe sysadmin.</span><span class="sxs-lookup"><span data-stu-id="bdf75-119">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="bdf75-120">Pour plus d’informations, consultez [Autorisations de point de terminaison GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bdf75-120">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bdf75-121">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bdf75-121">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-mirroring-endpoint-that-uses-windows-authentication"></a><span data-ttu-id="bdf75-122">Pour créer un point de terminaison de mise en miroir de bases de données qui utilise l'authentification Windows</span><span class="sxs-lookup"><span data-stu-id="bdf75-122">To Create a Database Mirroring Endpoint That Uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="bdf75-123">Connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur laquelle vous voulez créer un point de terminaison de mise en miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="bdf75-123">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to create a database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="bdf75-124">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="bdf75-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bdf75-125">Déterminez s'il existe déjà un point de terminaison de mise en miroir de base de données à l'aide de l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="bdf75-125">Determine if a database mirroring endpoint already exists by using the following statement:</span></span>  
  
    ```sql
    SELECT name, role_desc, state_desc FROM sys.database_mirroring_endpoints;
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bdf75-126">S'il existe déjà un point de terminaison de mise en miroir de base de données pour l'instance de serveur, utilisez-le pour toutes les autres sessions établies sur l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="bdf75-126">If a database mirroring endpoint already exists for the server instance, use that endpoint for any other sessions you establish on the server instance.</span></span>  
  
4.  <span data-ttu-id="bdf75-127">Pour utiliser Transact-SQL afin de créer un point de terminaison qui sera utilisé avec l'authentification Windows, utilisez une instruction CREATE ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="bdf75-127">To use Transact-SQL to create an endpoint to use with Windows Authentication, use a CREATE ENDPOINT statement.</span></span> <span data-ttu-id="bdf75-128">L'instruction prend la forme générale suivante :</span><span class="sxs-lookup"><span data-stu-id="bdf75-128">The statement takes the following general form:</span></span>  
  
     <span data-ttu-id="bdf75-129">CREATE ENDPOINT *\<endpointName>*</span><span class="sxs-lookup"><span data-stu-id="bdf75-129">CREATE ENDPOINT *\<endpointName>*</span></span>  
  
     <span data-ttu-id="bdf75-130">STATE=STARTED</span><span class="sxs-lookup"><span data-stu-id="bdf75-130">STATE=STARTED</span></span>  
  
     <span data-ttu-id="bdf75-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span><span class="sxs-lookup"><span data-stu-id="bdf75-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span></span>  
  
     <span data-ttu-id="bdf75-132">FOR DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="bdf75-132">FOR DATABASE_MIRRORING</span></span>  
  
     <span data-ttu-id="bdf75-133">(</span><span class="sxs-lookup"><span data-stu-id="bdf75-133">(</span></span>  
  
     <span data-ttu-id="bdf75-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span><span class="sxs-lookup"><span data-stu-id="bdf75-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span></span>  
  
     <span data-ttu-id="bdf75-135">]</span><span class="sxs-lookup"><span data-stu-id="bdf75-135">]</span></span>  
  
     <span data-ttu-id="bdf75-136">[ [ **,** ] ENCRYPTION = **REQUIRED**</span><span class="sxs-lookup"><span data-stu-id="bdf75-136">[ [**,**] ENCRYPTION = **REQUIRED**</span></span>  
  
     <span data-ttu-id="bdf75-137">[ ALGORITHM { *\<algorithm>* } ]</span><span class="sxs-lookup"><span data-stu-id="bdf75-137">[ ALGORITHM { *\<algorithm>* } ]</span></span>  
  
     <span data-ttu-id="bdf75-138">]</span><span class="sxs-lookup"><span data-stu-id="bdf75-138">]</span></span>  
  
     <span data-ttu-id="bdf75-139">[ **,** ] ROLE = *\<role>*</span><span class="sxs-lookup"><span data-stu-id="bdf75-139">[**,**] ROLE = *\<role>*</span></span>  
  
     <span data-ttu-id="bdf75-140">)</span><span class="sxs-lookup"><span data-stu-id="bdf75-140">)</span></span>  
  
     <span data-ttu-id="bdf75-141">where</span><span class="sxs-lookup"><span data-stu-id="bdf75-141">where</span></span>  
  
    -   <span data-ttu-id="bdf75-142">*\<endpointName>* représente le nom unique du point de terminaison de mise en miroir de base de données de l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="bdf75-142">*\<endpointName>* is a unique name for the database mirroring endpoint of the server instance.</span></span>  
  
    -   <span data-ttu-id="bdf75-143">STARTED spécifie que le point de terminaison doit être démarré et commencer à écouter les connexions.</span><span class="sxs-lookup"><span data-stu-id="bdf75-143">STARTED specifies that the endpoint is to be started and to begin listening for connections.</span></span> <span data-ttu-id="bdf75-144">Un point de terminaison de mise en miroir de base de données est en général créé dans l'état STARTED.</span><span class="sxs-lookup"><span data-stu-id="bdf75-144">A database mirroring endpoint typically is created in the STARTED state.</span></span> <span data-ttu-id="bdf75-145">D'une autre manière, vous pouvez démarrer une session dans un état STOPPED (par défaut) ou DISABLED.</span><span class="sxs-lookup"><span data-stu-id="bdf75-145">Alternatively, you can start a session in a STOPPED state (the default) or DISABLED state.</span></span>  
  
    -   <span data-ttu-id="bdf75-146">*\<listenerPortList>* est un numéro de port unique (*nnnn*) sur lequel le serveur doit écouter les messages de mise en miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="bdf75-146">*\<listenerPortList>* is a single port number (*nnnn*) on which you want the server to listen for database mirroring messages.</span></span> <span data-ttu-id="bdf75-147">Seul le protocole TCP est autorisé ; la spécification d'un autre protocole produit une erreur.</span><span class="sxs-lookup"><span data-stu-id="bdf75-147">Only TCP is allowed; specifying any other protocol causes an error.</span></span>  
  
         <span data-ttu-id="bdf75-148">Un numéro de port peut servir une fois seulement pour chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="bdf75-148">A port number can be used only once per computer system.</span></span> <span data-ttu-id="bdf75-149">Un point de terminaison de mise en miroir de bases de données peut utiliser n'importe quel point disponible sur le système local lors de la création du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="bdf75-149">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="bdf75-150">Pour identifier les ports en cours d'utilisation par les points de terminaison TCP, utilisez l'instruction Transact-SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="bdf75-150">To identify the ports currently being used by TCP endpoints on the system, use the following Transact-SQL statement:</span></span>  
  
        ```  
        SELECT name, port FROM sys.tcp_endpoints;  
        ```  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="bdf75-151">Chaque instance de serveur nécessite un port d'écoute et un seul.</span><span class="sxs-lookup"><span data-stu-id="bdf75-151">Each server instance requires one and only one unique listener port.</span></span>  
  
    -   <span data-ttu-id="bdf75-152">Pour l'authentification Windows, l'option AUTHENTICATION est facultative, à moins que vous vouliez que le point de terminaison utilise uniquement NTLM ou Kerberos pour authentifier les connexions.</span><span class="sxs-lookup"><span data-stu-id="bdf75-152">For Windows Authentication, the AUTHENTICATION option is optional, unless you want the endpoint to use only NTLM or Kerberos to authenticate connections.</span></span> <span data-ttu-id="bdf75-153">*\<authorizationMethod>* spécifie la méthode utilisée pour authentifier les connexions parmi l’une des suivantes : NTLM, KERBEROS ou NEGOTIATE.</span><span class="sxs-lookup"><span data-stu-id="bdf75-153">*\<authorizationMethod>* specifies the method used to authenticate connections as one of the following: NTLM, KERBEROS, or NEGOTIATE.</span></span> <span data-ttu-id="bdf75-154">NEGOTIATE, méthode par défaut, impose au point de terminaison d'utiliser le protocole de négociation Windows pour choisir NTLM ou Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bdf75-154">The default, NEGOTIATE, causes the endpoint to use the Windows negotiation protocol to choose either NTLM or Kerberos.</span></span> <span data-ttu-id="bdf75-155">La négociation active les connexions avec ou sans authentification, selon le niveau d'authentification du point de terminaison opposé.</span><span class="sxs-lookup"><span data-stu-id="bdf75-155">Negotiation enables connections with or without authentication, depending on the authentication level of the opposite endpoint.</span></span>  
  
    -   <span data-ttu-id="bdf75-156">ENCRYPTION est défini sur REQUIRED par défaut.</span><span class="sxs-lookup"><span data-stu-id="bdf75-156">ENCRYPTION is set to REQUIRED by default.</span></span> <span data-ttu-id="bdf75-157">En d'autres termes, toutes les connexions à ce point de terminaison doivent utiliser le chiffrement.</span><span class="sxs-lookup"><span data-stu-id="bdf75-157">This means that all connections to this endpoint must use encryption.</span></span> <span data-ttu-id="bdf75-158">Toutefois, vous pouvez désactiver le chiffrement ou le rendre facultatif sur un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="bdf75-158">However, you can disable encryption or make it optional on an endpoint.</span></span> <span data-ttu-id="bdf75-159">Les alternatives sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="bdf75-159">The alternatives are as follows:</span></span>  
  
        |<span data-ttu-id="bdf75-160">Valeur</span><span class="sxs-lookup"><span data-stu-id="bdf75-160">Value</span></span>|<span data-ttu-id="bdf75-161">Définition</span><span class="sxs-lookup"><span data-stu-id="bdf75-161">Definition</span></span>|  
        |-----------|----------------|  
        |<span data-ttu-id="bdf75-162">DISABLED</span><span class="sxs-lookup"><span data-stu-id="bdf75-162">DISABLED</span></span>|<span data-ttu-id="bdf75-163">Spécifie que les données envoyées sur une connexion ne sont pas chiffrées.</span><span class="sxs-lookup"><span data-stu-id="bdf75-163">Specifies that data sent over a connection is not encrypted.</span></span>|  
        |<span data-ttu-id="bdf75-164">SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="bdf75-164">SUPPORTED</span></span>|<span data-ttu-id="bdf75-165">Spécifie que les données sont chiffrées uniquement si le point de terminaison opposé spécifie SUPPORTED ou REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="bdf75-165">Specifies that the data is encrypted only if the opposite endpoint specifies either SUPPORTED or REQUIRED.</span></span>|  
        |<span data-ttu-id="bdf75-166">REQUIRED</span><span class="sxs-lookup"><span data-stu-id="bdf75-166">REQUIRED</span></span>|<span data-ttu-id="bdf75-167">Spécifie que les données envoyées sur une connexion doivent être chiffrées.</span><span class="sxs-lookup"><span data-stu-id="bdf75-167">Specifies that data sent over a connection must be encrypted.</span></span>|  
  
         <span data-ttu-id="bdf75-168">Si un point de terminaison exige un chiffrement, l'autre point de terminaison doit avoir l'instruction ENCRYPTION définie sur SUPPORTED ou REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="bdf75-168">If an endpoint requires encryption, the other endpoint must have ENCRYPTION set to either SUPPORTED or REQUIRED.</span></span>  
  
    -   <span data-ttu-id="bdf75-169">*\<algorithm>* propose la possibilité de spécifier les normes de chiffrement du point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="bdf75-169">*\<algorithm>* provides the option of specifying the encryption standards for the endpoint.</span></span> <span data-ttu-id="bdf75-170">La valeur de *\<algorithm>* peut être l'un des algorithmes ou combinaisons d'algorithmes suivants : RC4, AES, AES RC4 ou RC4 AES.</span><span class="sxs-lookup"><span data-stu-id="bdf75-170">The value of *\<algorithm>* can be one following algorithms or combinations of algorithms: RC4, AES, AES RC4, or RC4 AES.</span></span>  
  
         <span data-ttu-id="bdf75-171">AES RC4 spécifie que ce point de terminaison va négocier l'algorithme de chiffrement et donner la préférence à l'algorithme AES.</span><span class="sxs-lookup"><span data-stu-id="bdf75-171">AES RC4 specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the AES algorithm.</span></span> <span data-ttu-id="bdf75-172">RC4 AES spécifie que ce point de terminaison va négocier l'algorithme de chiffrement et donner la préférence à l'algorithme RC4.</span><span class="sxs-lookup"><span data-stu-id="bdf75-172">RC4 AES specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the RC4 algorithm.</span></span> <span data-ttu-id="bdf75-173">Si les deux points de terminaison spécifient les deux algorithmes mais dans des ordres différents, le point de terminaison acceptant la connexion a le dernier mot.</span><span class="sxs-lookup"><span data-stu-id="bdf75-173">If both endpoints specify both algorithms but in different orders, the endpoint accepting the connection wins.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="bdf75-174">L'algorithme RC4 est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="bdf75-174">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="bdf75-175">Nous vous recommandons d'utiliser AES.</span><span class="sxs-lookup"><span data-stu-id="bdf75-175">We recommend that you use AES.</span></span>  
  
    -   <span data-ttu-id="bdf75-176">*\<role>* définit le ou les rôles que le serveur peut endosser.</span><span class="sxs-lookup"><span data-stu-id="bdf75-176">*\<role>* defines the role or roles that the server can perform.</span></span> <span data-ttu-id="bdf75-177">La spécification de ROLE est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="bdf75-177">Specifying ROLE is required.</span></span> <span data-ttu-id="bdf75-178">Toutefois, le rôle du point de terminaison concerne uniquement la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="bdf75-178">However, the role of the endpoint is relevant only for database mirroring.</span></span> <span data-ttu-id="bdf75-179">Pour [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], le rôle du point de terminaison est ignoré.</span><span class="sxs-lookup"><span data-stu-id="bdf75-179">For [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], the role of the endpoint is ignored.</span></span>  
  
         <span data-ttu-id="bdf75-180">Pour qu'une instance de serveur puisse occuper un rôle pour une session de mise en miroir de base de données et un rôle différent pour une autre session, spécifiez ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="bdf75-180">To allow a server instance to serve as one role for one database mirroring session and different role for another session, specify ROLE=ALL.</span></span> <span data-ttu-id="bdf75-181">Pour restreindre la fonction d'une instance de serveur à partenaire ou témoin, spécifiez ROLE=PARTNER ou ROLE=WITNESS respectivement.</span><span class="sxs-lookup"><span data-stu-id="bdf75-181">To restrict a server instance to being either a partner or a witness, specify ROLE=PARTNER or ROLE=WITNESS, respectively.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="bdf75-182">Pour plus d'informations sur les options de mise en miroir de bases de données pour les différentes éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="bdf75-182">For more information about Database Mirroring options for different editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
     <span data-ttu-id="bdf75-183">Pour une description complète de la syntaxe de CREATE ENDPOINT, consultez [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bdf75-183">For a complete description of the CREATE ENDPOINT syntax, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bdf75-184">Pour modifier un point de terminaison existant, utilisez [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bdf75-184">To change an existing endpoint, use [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
###  <a name="example-creating-endpoints-to-support-for-database-mirroring-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="bdf75-185">Exemple : Création de points de terminaison pour prendre en charge la mise en miroir de bases de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bdf75-185">Example: Creating Endpoints to Support for Database Mirroring (Transact-SQL)</span></span>  
 <span data-ttu-id="bdf75-186">L'exemple suivant crée des points de terminaison de mise en miroir de bases de données pour les instances de serveur par défaut sur trois systèmes informatiques distincts :</span><span class="sxs-lookup"><span data-stu-id="bdf75-186">The following example creates database mirroring endpoints for the default server instances on three separate computer systems:</span></span>  
  
|<span data-ttu-id="bdf75-187">Rôle de l'instance de serveur</span><span class="sxs-lookup"><span data-stu-id="bdf75-187">Role of server instance</span></span>|<span data-ttu-id="bdf75-188">Nom de l'ordinateur hôte</span><span class="sxs-lookup"><span data-stu-id="bdf75-188">Name of host computer</span></span>|  
|-----------------------------|---------------------------|  
|<span data-ttu-id="bdf75-189">Partenaire (au départ, dans le rôle de principal)</span><span class="sxs-lookup"><span data-stu-id="bdf75-189">Partner (initially in the principal role)</span></span>|`SQLHOST01\.`|  
|<span data-ttu-id="bdf75-190">Partenaire (au départ, dans le rôle de serveur miroir)</span><span class="sxs-lookup"><span data-stu-id="bdf75-190">Partner (initially in the mirror role)</span></span>|`SQLHOST02\.`|  
|<span data-ttu-id="bdf75-191">Témoin</span><span class="sxs-lookup"><span data-stu-id="bdf75-191">Witness</span></span>|`SQLHOST03\.`|  
  
 <span data-ttu-id="bdf75-192">Dans cet exemple, les trois points de terminaison utilisent le numéro de port 7022, bien que n'importe quel autre numéro de port disponible pourrait convenir.</span><span class="sxs-lookup"><span data-stu-id="bdf75-192">In this example, all three endpoints use port number 7022, though any available port number would work.</span></span> <span data-ttu-id="bdf75-193">L'option AUTHENTICATION est inutile puisque les points de terminaison utilisent le type par défaut, c'est-à-dire l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="bdf75-193">The AUTHENTICATION option is unnecessary, because the endpoints use the default type, Windows Authentication.</span></span> <span data-ttu-id="bdf75-194">L'option ENCRYPTION est également inutile dans la mesure où la négociation de la méthode d'authentification d'une connexion est prévue sur tous les points de terminaison, ce qui correspond au comportement par défaut de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="bdf75-194">The ENCRYPTION option is also unnecessary, because the endpoints are all intended to negotiate the authentication method for a connection, which is the default behavior for Windows Authentication.</span></span> <span data-ttu-id="bdf75-195">Également caractéristique de ce comportement par défaut, le chiffrement est obligatoire sur tous les points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="bdf75-195">Also, all of the endpoints require the encryption, which is the default behavior.</span></span>  
  
 <span data-ttu-id="bdf75-196">Chaque instance de serveur est limitée à un rôle exclusif de partenaire ou de témoin, ce rôle est expressément spécifié par le point de terminaison de chaque serveur (ROLE=PARTNER ou ROLE=WITNESS).</span><span class="sxs-lookup"><span data-stu-id="bdf75-196">Each server instance is limited to serving as either a partner or a witness, and the endpoint of each server expressly specifies which role (ROLE=PARTNER or ROLE=WITNESS).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bdf75-197">Chaque instance de serveur ne peut disposer que d'un seul point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="bdf75-197">Each server instance can have only one endpoint.</span></span> <span data-ttu-id="bdf75-198">Ainsi, pour utiliser une instance de serveur tour à tour comme partenaire dans certaines sessions ou témoin dans d'autres, spécifiez ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="bdf75-198">Therefore, if you want a server instance to be a partner in some sessions and the witness in others, specify ROLE=ALL.</span></span>  
  
```sql
--Endpoint for initial principal server instance, which  
--is the only server instance running on SQLHOST01.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for initial mirror server instance, which  
--is the only server instance running on SQLHOST02.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for witness server instance, which  
--is the only server instance running on SQLHOST03.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=WITNESS);  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="bdf75-199">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="bdf75-199">Related Tasks</span></span>  

### <a name="to-configure-a-database-mirroring-endpoint"></a><span data-ttu-id="bdf75-200">Pour configurer un point de terminaison de mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="bdf75-200">To Configure a Database Mirroring Endpoint</span></span>
  
-   [<span data-ttu-id="bdf75-201">Créer un point de terminaison de mise en miroir de bases de données pour groupes de disponibilité AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf75-201">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](../availability-groups/windows/database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="bdf75-202">Utiliser des certificats pour un point de terminaison de mise en miroir de bases de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf75-202">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="bdf75-203">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf75-203">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="bdf75-204">Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf75-204">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="bdf75-205">Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf75-205">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="bdf75-206">Spécifier l’URL de point de terminaison lors de l’ajout ou lors de la modification d’un réplica de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf75-206">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](../availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="bdf75-207">**Pour afficher des informations sur le point de terminaison de mise en miroir de bases de données**</span><span class="sxs-lookup"><span data-stu-id="bdf75-207">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="bdf75-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf75-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="bdf75-209">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bdf75-209">See Also</span></span>  
 <span data-ttu-id="bdf75-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bdf75-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="bdf75-211">[Choisir un algorithme de chiffrement](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="bdf75-211">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="bdf75-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bdf75-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="bdf75-213">[Spécifier une adresse réseau de serveur &#40;mise en miroir de bases de données&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="bdf75-213">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="bdf75-214">[Exemple : Configuration de la mise en miroir de bases de données à l’aide de l’authentification Windows &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="bdf75-214">[Example: Setting Up Database Mirroring Using Windows Authentication &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="bdf75-215">Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf75-215">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
