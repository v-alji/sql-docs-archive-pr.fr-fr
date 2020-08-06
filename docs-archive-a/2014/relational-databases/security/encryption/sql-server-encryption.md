---
title: Chiffrement SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], about encryption
- security [SQL Server], encryption
- cryptography [SQL Server], about cryptography
ms.assetid: ead0150e-4943-4ad5-84c8-36f85c7278f4
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 6fc68e6f3280a8e23d6a1bf4f364aadfffd69f85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710511"
---
# <a name="sql-server-encryption"></a><span data-ttu-id="ecbe9-102">Chiffrement SQL Server</span><span class="sxs-lookup"><span data-stu-id="ecbe9-102">SQL Server Encryption</span></span>
  <span data-ttu-id="ecbe9-103">Le chiffrement est un processus visant à rendre des données inintelligibles à l'aide d'une clé ou d'un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-103">Encryption is the process of obfuscating data by the use of a key or password.</span></span> <span data-ttu-id="ecbe9-104">Les données sont alors inutiles en l'absence du mot de passe ou de la clé de déchiffrement correspondante.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-104">This can make the data useless without the corresponding decryption key or password.</span></span> <span data-ttu-id="ecbe9-105">Le chiffrement ne résout pas les problèmes de contrôle d'accès.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-105">Encryption does not solve access control problems.</span></span> <span data-ttu-id="ecbe9-106">Toutefois, il améliore la sécurité en limitant les pertes de données même si les contrôles d'accès sont contournés.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-106">However, it enhances security by limiting data loss even if access controls are bypassed.</span></span> <span data-ttu-id="ecbe9-107">Par exemple, si l'ordinateur hôte de la base de données est mal configuré et qu'un pirate parvient à se procurer des données sensibles, les données subtilisées seront vraisemblablement inexploitables si elles sont chiffrées.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-107">For example, if the database host computer is misconfigured and a hacker obtains sensitive data, that stolen information might be useless if it is encrypted.</span></span>  
  
 <span data-ttu-id="ecbe9-108">Vous pouvez utiliser le chiffrement dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour les connexions, les données et les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-108">You can use encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for connections, data, and stored procedures.</span></span> <span data-ttu-id="ecbe9-109">Le tableau ci-dessous contient davantage d'informations sur le chiffrement dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecbe9-109">The following table contains more information about encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ecbe9-110">Bien que le chiffrement soit un outil précieux qui aide à garantir la sécurité, il ne doit pas être envisagé pour toutes les données et connexions.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-110">Although encryption is a valuable tool to help ensure security, it should not be considered for all data or connections.</span></span> <span data-ttu-id="ecbe9-111">Lorsque vous décidez de mettre en œuvre ou non le chiffrement, tenez compte de la manière dont les utilisateurs accèderont aux données.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-111">When you are deciding whether to implement encryption, consider how users will access data.</span></span> <span data-ttu-id="ecbe9-112">Si les utilisateurs accèdent aux données via un réseau public, le chiffrement des données peut être requis pour augmenter la sécurité.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-112">If users access data over a public network, data encryption might be required to increase security.</span></span> <span data-ttu-id="ecbe9-113">Toutefois, si tous les accès impliquent une configuration intranet sécurisée, le chiffrement peut s'avérer superflu.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-113">However, if all access involves a secure intranet configuration, encryption might not be required.</span></span> <span data-ttu-id="ecbe9-114">Toute utilisation du chiffrement doit également inclure une stratégie de maintenance pour les mots de passe, les clés et les certificats.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-114">Any use of encryption should also include a maintenance strategy for passwords, keys, and certificates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ecbe9-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ecbe9-115">In This Section</span></span>  
 [<span data-ttu-id="ecbe9-116">Hiérarchie de chiffrement</span><span class="sxs-lookup"><span data-stu-id="ecbe9-116">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
 <span data-ttu-id="ecbe9-117">Informations sur la hiérarchie de chiffrement dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecbe9-117">Information about the encryption hierarchy in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ecbe9-118">Choisir un algorithme de chiffrement</span><span class="sxs-lookup"><span data-stu-id="ecbe9-118">Choose an Encryption Algorithm</span></span>](choose-an-encryption-algorithm.md)  
 <span data-ttu-id="ecbe9-119">Informations sur la manière de sélectionner un algorithme de chiffrement efficace.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-119">Information about how to select an effective encrypting algorithm.</span></span>  
  
 [<span data-ttu-id="ecbe9-120">Chiffrement transparent des données &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbe9-120">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)  
 <span data-ttu-id="ecbe9-121">Informations générales sur la manière de chiffrer des données de façon transparente.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-121">General information about how to encrypt data transparently.</span></span>  
  
 [<span data-ttu-id="ecbe9-122">SQL Server et clés de chiffrement de base de données &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbe9-122">SQL Server and Database Encryption Keys &#40;Database Engine&#41;</span></span>](sql-server-and-database-encryption-keys-database-engine.md)  
 <span data-ttu-id="ecbe9-123">Dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], les clés de chiffrement incluent une combinaison d'une clé publique, d'une clé privée et d'une clé symétrique, dont le but est de protéger les données sensibles.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-123">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], encryption keys include a combination of public, private, and symmetric keys that are used to protect sensitive data.</span></span> <span data-ttu-id="ecbe9-124">Cette section explique comment implémenter et gérer des clés de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-124">This section explains how to implement and manage encryption keys.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="ecbe9-125">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="ecbe9-125">Related Content</span></span>  
 [<span data-ttu-id="ecbe9-126">Sécurisation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ecbe9-126">Securing SQL Server</span></span>](../securing-sql-server.md)  
 <span data-ttu-id="ecbe9-127">Vue d'ensemble du processus permettant de mieux sécuriser la plateforme [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et du travail avec des utilisateurs et des objets sécurisables.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-127">Overview of how to help secure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] platform, and how to work with users and securable objects.</span></span>  
  
 [<span data-ttu-id="ecbe9-128">Fonctions de chiffrement &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbe9-128">Cryptographic Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cryptographic-functions-transact-sql)  
 <span data-ttu-id="ecbe9-129">Informations sur la manière d'implémenter des fonctions de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-129">Information about how to implement cryptographic functions.</span></span>  
  
 [<span data-ttu-id="ecbe9-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbe9-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbypassphrase-transact-sql)  
 <span data-ttu-id="ecbe9-131">Informations sur l'utilisation d'un mot de passe pour chiffrer des données.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-131">Information about how to use a password to encrypt data.</span></span>  
  
 [<span data-ttu-id="ecbe9-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbe9-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
 <span data-ttu-id="ecbe9-133">Informations sur l'utilisation d'une clé symétrique pour chiffrer des données.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-133">Information about how to use a symmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="ecbe9-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbe9-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbyasymkey-transact-sql)  
 <span data-ttu-id="ecbe9-135">Informations sur l'utilisation d'une clé asymétrique pour chiffrer des données.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-135">Information about how to use an asymmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="ecbe9-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ecbe9-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbycert-transact-sql)  
 <span data-ttu-id="ecbe9-137">Informations sur l'utilisation d'un certificat pour chiffrer des données.</span><span class="sxs-lookup"><span data-stu-id="ecbe9-137">Information about how to use a certificate to encrypt data.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="ecbe9-138">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="ecbe9-138">External Resources</span></span>  
 [<span data-ttu-id="ecbe9-139">10 étapes pour SQL Server la sécurité 2005</span><span class="sxs-lookup"><span data-stu-id="ecbe9-139">10 Steps to SQL Server 2005 Security</span></span>](https://www.itprotoday.com/sql-server/10-steps-sql-server-2005-security)  
 <span data-ttu-id="ecbe9-140">Informations à jour sur la sécurité [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ecbe9-140">Current information about [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbe9-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ecbe9-141">See Also</span></span>  
 <span data-ttu-id="ecbe9-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ecbe9-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span></span>  
 <span data-ttu-id="ecbe9-143">[SQL Server et clés de chiffrement de base de données &#40;moteur de base de données&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="ecbe9-143">[SQL Server and Database Encryption Keys &#40;Database Engine&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span></span>  
 [<span data-ttu-id="ecbe9-144">Sauvegarder et restaurer les clés de chiffrement Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ecbe9-144">Back Up and Restore Reporting Services Encryption Keys</span></span>](../../../reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)  
  
  
