---
title: Clé principale du service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server]
- service master key [SQL Server], about service master key
ms.assetid: 85f2095d-2590-4f59-8a29-7e100edd02bb
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: baeeffd49ac89ce85cf64932fbfd4982d7243887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710520"
---
# <a name="service-master-key"></a><span data-ttu-id="402f2-102">clé principale de service</span><span class="sxs-lookup"><span data-stu-id="402f2-102">Service Master Key</span></span>
  <span data-ttu-id="402f2-103">La clé principale du service représente la racine de la hiérarchie de chiffrement de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="402f2-103">The Service Master Key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="402f2-104">Elle est générée automatiquement la première fois qu'il est nécessaire de chiffrer une autre clé.</span><span class="sxs-lookup"><span data-stu-id="402f2-104">It is generated automatically the first time it is needed to encrypt another key.</span></span> <span data-ttu-id="402f2-105">Par défaut, la clé principale du service est chiffrée à l'aide de l'API de protection des données (DPAPI) Windows et de la clé de la machine locale.</span><span class="sxs-lookup"><span data-stu-id="402f2-105">By default, the Service Master Key is encrypted using the Windows data protection API and using the local machine key.</span></span> <span data-ttu-id="402f2-106">La clé principale du service ne peut être ouverte que par le compte de service Windows sous lequel elle a été créée ou par un principal ayant accès au nom du compte de service et à son mot de passe.</span><span class="sxs-lookup"><span data-stu-id="402f2-106">The Service Master Key can only be opened by the Windows service account under which it was created or by a principal with access to both the service account name and its password.</span></span>  
  
 <span data-ttu-id="402f2-107">La régénération ou la restauration de la clé principale du service implique le déchiffrement puis le chiffrement de la hiérarchie complète de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="402f2-107">Regenerating or restoring the Service Master Key involves decrypting and re-encrypting the complete encryption hierarchy.</span></span> <span data-ttu-id="402f2-108">À moins que l'intégrité de la clé n'ait été compromise, cette opération nécessitant de nombreuses ressources doit être planifiée pendant une période où la demande est faible.</span><span class="sxs-lookup"><span data-stu-id="402f2-108">Unless the key has been compromised, this resource-intensive operation should be scheduled during a period of low demand.</span></span>  
  
 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] <span data-ttu-id="402f2-109">utilise l’algorithme de chiffrement AES pour protéger la clé principale du service (SMK) et la clé principale de base de données (DMK).</span><span class="sxs-lookup"><span data-stu-id="402f2-109">uses the AES encryption algorithm to protect the service master key (SMK) and the database master key (DMK).</span></span> <span data-ttu-id="402f2-110">AES est un algorithme de chiffrement plus récent que 3DES, qui était utilisé dans les versions antérieures.</span><span class="sxs-lookup"><span data-stu-id="402f2-110">AES is a newer encryption algorithm than 3DES used in earlier versions.</span></span> <span data-ttu-id="402f2-111">Au terme de la mise à niveau d'une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] vers [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , les clés SMK et DMK doivent être régénérées pour mettre à niveau les clés principales vers AES.</span><span class="sxs-lookup"><span data-stu-id="402f2-111">After upgrading an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] the SMK and DMK should be regenerated in order to upgrade the master keys to AES.</span></span> <span data-ttu-id="402f2-112">Pour plus d’informations sur la régénération de la clé SMK, consultez [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) et [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="402f2-112">For more information about regenerating the SMK, see [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) and [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="402f2-113">Bonne pratique</span><span class="sxs-lookup"><span data-stu-id="402f2-113">Best Practice</span></span>  
 <span data-ttu-id="402f2-114">Sauvegardez la clé principale du service et stockez la copie sauvegardée en un lieu sûr, hors site.</span><span class="sxs-lookup"><span data-stu-id="402f2-114">Back up the Service Master Key and store the backed up copy in a secure, off-site location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="402f2-115">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="402f2-115">Related Tasks</span></span>  
 [<span data-ttu-id="402f2-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="402f2-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-service-master-key-transact-sql)  
  
 [<span data-ttu-id="402f2-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="402f2-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-service-master-key-transact-sql)  
  
 [<span data-ttu-id="402f2-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="402f2-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-service-master-key-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="402f2-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="402f2-119">See Also</span></span>  
 [<span data-ttu-id="402f2-120">Hiérarchie de chiffrement</span><span class="sxs-lookup"><span data-stu-id="402f2-120">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
