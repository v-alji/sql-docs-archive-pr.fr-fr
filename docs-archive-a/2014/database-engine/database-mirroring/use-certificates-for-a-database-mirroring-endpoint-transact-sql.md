---
title: Utiliser des certificats pour un point de terminaison de mise en miroir de bases de données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: f7c23cc2-48dc-4b78-b441-89ca29a0bd9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c159e66e798524c41bf6e653283c299cc8393be5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604128"
---
# <a name="use-certificates-for-a-database-mirroring-endpoint-transact-sql"></a><span data-ttu-id="25977-102">Utiliser des certificats pour un point de terminaison de mise en miroir de bases de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="25977-102">Use Certificates for a Database Mirroring Endpoint (Transact-SQL)</span></span>
  <span data-ttu-id="25977-103">Pour activer l'authentification des certificats en vue de la mise en miroir de bases de données sur une instance déterminée du serveur, l'administrateur système doit configurer chaque instance du serveur afin d'utiliser les certificats à la fois sur les connexions sortantes et entrantes.</span><span class="sxs-lookup"><span data-stu-id="25977-103">To enable certificate authentication for database mirroring on a given server instance, the system administrator must configure each server instance to use certificates on both outbound and inbound connections.</span></span> <span data-ttu-id="25977-104">Les connexions sortantes doivent être configurées en premier.</span><span class="sxs-lookup"><span data-stu-id="25977-104">Outbound connections must be configured first.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25977-105">Toutes les connexions de mise en miroir situées sur une instance du serveur utilisent un point de terminaison de mise en miroir de bases de données unique, et vous devez spécifier la méthode d'authentification de l'instance du serveur au moment de la création de ce point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="25977-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span> <span data-ttu-id="25977-106">Par conséquent, vous ne pouvez utiliser qu'une forme d'authentification par instance du serveur pour la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="25977-106">Therefore, you can use only one form of authentication per server instance for database mirroring.</span></span>  
  
## <a name="configuring-outbound-connections"></a><span data-ttu-id="25977-107">Configuration des connexions sortantes</span><span class="sxs-lookup"><span data-stu-id="25977-107">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="25977-108">Procédez comme suit sur chaque instance du serveur que vous configurez pour la mise en miroir de bases de données :</span><span class="sxs-lookup"><span data-stu-id="25977-108">Follow these steps on each server instance that you are configuring for database mirroring:</span></span>  
  
1.  <span data-ttu-id="25977-109">Dans la base de données **master** , créez une clé principale de base de données.</span><span class="sxs-lookup"><span data-stu-id="25977-109">In the **master** database, create a database master key.</span></span>  
  
2.  <span data-ttu-id="25977-110">Dans la base de données **master** , créez un certificat chiffré sur l’instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="25977-110">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="25977-111">Créez un point de terminaison pour l'instance du serveur à l'aide de son certificat.</span><span class="sxs-lookup"><span data-stu-id="25977-111">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="25977-112">Sauvegardez le certificat dans un fichier et copiez-le par sécurité sur un ou plusieurs autres systèmes.</span><span class="sxs-lookup"><span data-stu-id="25977-112">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="25977-113">Vous devez exécuter cette procédure pour chaque partenaire et pour le témoin éventuel.</span><span class="sxs-lookup"><span data-stu-id="25977-113">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="25977-114">Pour plus d’informations, consultez [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions sortantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="25977-114">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
## <a name="configuring-inbound-connections"></a><span data-ttu-id="25977-115">Configuration des connexions entrantes</span><span class="sxs-lookup"><span data-stu-id="25977-115">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="25977-116">Ensuite, procédez comme suit pour chaque partenaire que vous configurez pour la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="25977-116">Next, follow these steps for each partner that you are configuring for database mirroring.</span></span> <span data-ttu-id="25977-117">Dans la base de données **master** :</span><span class="sxs-lookup"><span data-stu-id="25977-117">In the **master** database:</span></span>  
  
1.  <span data-ttu-id="25977-118">Créez une connexion pour l'autre système.</span><span class="sxs-lookup"><span data-stu-id="25977-118">Create a login for the other system.</span></span>  
  
2.  <span data-ttu-id="25977-119">Créez un utilisateur pour cette connexion.</span><span class="sxs-lookup"><span data-stu-id="25977-119">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="25977-120">Obtenez le certificat pour la mise en miroir du point de terminaison de l'autre instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="25977-120">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="25977-121">Associez le certificat à l'utilisateur créé à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="25977-121">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="25977-122">Accordez à ce point de terminaison de mise en miroir l'autorisation CONNECT sur la connexion.</span><span class="sxs-lookup"><span data-stu-id="25977-122">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="25977-123">S'il existe un témoin, vous devez également configurer les connexions entrantes pour celui-ci.</span><span class="sxs-lookup"><span data-stu-id="25977-123">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="25977-124">Cela exige la définition des noms de connexion, des utilisateurs et des certificats pour le témoin sur les deux partenaires, et inversement.</span><span class="sxs-lookup"><span data-stu-id="25977-124">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="25977-125">Pour plus d’informations, consultez [Autoriser un point de terminaison de mise en miroir de bases de données à utiliser des certificats pour les connexions entrantes &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="25977-125">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="25977-126">Sécurité</span><span class="sxs-lookup"><span data-stu-id="25977-126">Security</span></span>  
 <span data-ttu-id="25977-127">À moins que vous ne puissiez garantir la sécurité de votre réseau, il est recommandé d'utiliser le chiffrement pour les connexions de mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="25977-127">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span> <span data-ttu-id="25977-128">Pour plus d’informations, consultez [Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="25977-128">For more information, see [The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span></span>  
  
 <span data-ttu-id="25977-129">Lors de la copie d'un certificat sur un autre système, utilisez une méthode de copie sécurisée.</span><span class="sxs-lookup"><span data-stu-id="25977-129">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="25977-130">Veillez particulièrement à sécuriser tous vos certificats.</span><span class="sxs-lookup"><span data-stu-id="25977-130">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25977-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25977-131">See Also</span></span>  
 <span data-ttu-id="25977-132">[Créer une clé principale de base de données](../../relational-databases/security/encryption/create-a-database-master-key.md) </span><span class="sxs-lookup"><span data-stu-id="25977-132">[Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md) </span></span>  
 <span data-ttu-id="25977-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25977-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="25977-134">[Sécurité de transport pour la mise en miroir de bases de données et les groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="25977-134">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="25977-135">[Centre de sécurité pour le moteur de base de données SQL Server et Azure SQL Database](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span><span class="sxs-lookup"><span data-stu-id="25977-135">[Security Center for SQL Server Database Engine and Azure SQL Database](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span></span>  
 [<span data-ttu-id="25977-136">Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="25977-136">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
