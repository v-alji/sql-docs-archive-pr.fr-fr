---
title: Choisir un algorithme de chiffrement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], algorithms
- encryption [SQL Server], algorithms
- security [SQL Server], encryption
- algorithms [SQL Server encryption]
ms.assetid: 8227028c-a9c9-489d-bd27-fbf8242634ae
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b2c5292b4a00a3ad81e53fdbc603bb584130613
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709083"
---
# <a name="choose-an-encryption-algorithm"></a><span data-ttu-id="52962-102">Choisir un algorithme de chiffrement</span><span class="sxs-lookup"><span data-stu-id="52962-102">Choose an Encryption Algorithm</span></span>
  <span data-ttu-id="52962-103">Le chiffrement est l'une des mesures préventives à la disposition des administrateurs qui souhaitent sécuriser une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52962-103">Encryption is one of several defenses-in-depth that are available to the administrator who wants to secure an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="52962-104">Les algorithmes de chiffrement définissent les transformations de données qui ne peuvent pas être facilement inversées par les utilisateurs non autorisés.</span><span class="sxs-lookup"><span data-stu-id="52962-104">Encryption algorithms define data transformations that cannot be easily reversed by unauthorized users.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="52962-105">permet aux administrateurs et aux développeurs de choisir entre plusieurs algorithmes, notamment DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, RC4 128 bits, DESX, AES 128 bits, AES 192 bits et AES 256 bits.</span><span class="sxs-lookup"><span data-stu-id="52962-105">allows administrators and developers to choose from among several algorithms, including DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span>  
  
 <span data-ttu-id="52962-106">Aucun algorithme unique ne convient pour toutes les situations et l'appréciation des avantages de chaque algorithme dépasse le cadre de la documentation en ligne de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52962-106">No single algorithm is ideal for all situations, and guidance on the merits of each is beyond the scope of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="52962-107">Cependant, les principes suivants s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="52962-107">However, the following general principles apply:</span></span>  
  
-   <span data-ttu-id="52962-108">Un chiffrement renforcé consomme en général davantage de ressources processeur qu'un chiffrement plus faible.</span><span class="sxs-lookup"><span data-stu-id="52962-108">Strong encryption generally consumes more CPU resources than weak encryption.</span></span>  
  
-   <span data-ttu-id="52962-109">Les clés longues produisent en général un chiffrement plus fort que les clés courtes.</span><span class="sxs-lookup"><span data-stu-id="52962-109">Long keys generally yield stronger encryption than short keys.</span></span>  
  
-   <span data-ttu-id="52962-110">À longueur de clé égale, le chiffrement asymétrique est plus faible que le chiffrement symétrique, mais il est relativement lent.</span><span class="sxs-lookup"><span data-stu-id="52962-110">Asymmetric encryption is weaker than symmetric encryption using the same key length, but it is relatively slow.</span></span>  
  
-   <span data-ttu-id="52962-111">Le chiffrement par blocs avec des clés longues est plus fort que le chiffrement par flux.</span><span class="sxs-lookup"><span data-stu-id="52962-111">Block ciphers with long keys are stronger than stream ciphers.</span></span>  
  
-   <span data-ttu-id="52962-112">Les mots de passe longs et complexes sont plus forts que les mots de passe courts.</span><span class="sxs-lookup"><span data-stu-id="52962-112">Long, complex passwords are stronger than short passwords.</span></span>  
  
-   <span data-ttu-id="52962-113">Si vous chiffrez de grandes quantités de données, vous devez utiliser pour cela une clé symétrique, puis chiffrer cette clé avec une clé asymétrique.</span><span class="sxs-lookup"><span data-stu-id="52962-113">If you are encrypting lots of data, you should encrypt the data using a symmetric key, and encrypt the symmetric key with an asymmetric key.</span></span>  
  
-   <span data-ttu-id="52962-114">Les données chiffrées ne peuvent pas être compressées, mais les données compressées peuvent être chiffrées.</span><span class="sxs-lookup"><span data-stu-id="52962-114">Encrypted data cannot be compressed, but compressed data can be encrypted.</span></span> <span data-ttu-id="52962-115">Si vous utilisez la compression, vous devez compresser les données avant de les chiffrer.</span><span class="sxs-lookup"><span data-stu-id="52962-115">If you use compression, you should compress data before encrypting it.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="52962-116">L'algorithme RC4 est uniquement pris en charge pour des raisons de compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="52962-116">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="52962-117">Le nouveau matériel ne peut être chiffré à l'aide de RC4 ou de RC4_128 que lorsque la base de données se trouve dans le niveau de compatibilité 90 ou 100.</span><span class="sxs-lookup"><span data-stu-id="52962-117">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="52962-118">(Non recommandé.) Utilisez à la place un algorithme plus récent, tel qu'un des algorithmes AES.</span><span class="sxs-lookup"><span data-stu-id="52962-118">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="52962-119">Dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] et les versions ultérieures, le matériel chiffré à l'aide de RC4 ou de RC4_128 peut être déchiffré dans n'importe quel niveau de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="52962-119">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] and higher material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
>   
>  <span data-ttu-id="52962-120">L'utilisation répétée du même RC4 ou RC4_128 KEY_GUID sur différents blocs de données entraîne la même clé RC4 car [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ne fournit pas automatiquement de salt.</span><span class="sxs-lookup"><span data-stu-id="52962-120">Repeated use of the same RC4 or RC4_128 KEY_GUID on different blocks of data will result in the same RC4 key because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not provide a salt automatically.</span></span> <span data-ttu-id="52962-121">L'utilisation répétée de la même clé RC4 est une erreur connue qui entraîne un chiffrement très faible.</span><span class="sxs-lookup"><span data-stu-id="52962-121">Using the same RC4 key repeatedly is a well-known error that will result in very weak encryption.</span></span> <span data-ttu-id="52962-122">Par conséquent, les mots clés RC4 et RC4_128 sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="52962-122">Therefore, we have deprecated the RC4 and RC4_128 keywords.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="52962-123">Pour plus d'informations sur les algorithmes et la technologie de chiffrement, consultez la rubrique [Concepts fondamentaux sur la sécurité](https://go.microsoft.com/fwlink/?LinkId=62082) dans le Guide du développeur .NET Framework sur le site MSDN.</span><span class="sxs-lookup"><span data-stu-id="52962-123">For more information about encryption algorithms and encryption technology, see [Key Security Concepts](https://go.microsoft.com/fwlink/?LinkId=62082) in the .NET Framework Developer's Guide on MSDN.</span></span>  
  
 <span data-ttu-id="52962-124">**Éclaircissement concernant les algorithmes DES :**</span><span class="sxs-lookup"><span data-stu-id="52962-124">**Clarification regarding DES algorithms:**</span></span>  
  
-   <span data-ttu-id="52962-125">DESX a été nommé incorrectement.</span><span class="sxs-lookup"><span data-stu-id="52962-125">DESX was incorrectly named.</span></span> <span data-ttu-id="52962-126">Les clés symétriques créées avec ALGORITHM = DESX utilisent en fait le chiffrement TRIPLE DES avec une clé de 192 bits.</span><span class="sxs-lookup"><span data-stu-id="52962-126">Symmetric keys created with ALGORITHM = DESX actually use the TRIPLE DES cipher with a 192-bit key.</span></span> <span data-ttu-id="52962-127">L'algorithme DESX n'est pas fourni.</span><span class="sxs-lookup"><span data-stu-id="52962-127">The DESX algorithm is not provided.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
-   <span data-ttu-id="52962-128">Les clés symétriques créées avec ALGORITHM = TRIPLE_DES_3KEY utilisent TRIPLE DES avec une clé de 192 bits.</span><span class="sxs-lookup"><span data-stu-id="52962-128">Symmetric keys created with ALGORITHM = TRIPLE_DES_3KEY use TRIPLE DES with a 192-bit key.</span></span>  
  
-   <span data-ttu-id="52962-129">Les clés symétriques créées avec ALGORITHM = TRIPLE_DES utilisent TRIPLE DES avec une clé de 128 bits.</span><span class="sxs-lookup"><span data-stu-id="52962-129">Symmetric keys created with ALGORITHM = TRIPLE_DES use TRIPLE DES with a 128-bit key.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="52962-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="52962-130">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52962-131">Chiffrement à l'aide d'une clé symétrique.</span><span class="sxs-lookup"><span data-stu-id="52962-131">Encrypting using a symmetric key.</span></span>|[<span data-ttu-id="52962-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52962-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)|  
|<span data-ttu-id="52962-133">Chiffrement à l'aide d'une clé asymétrique.</span><span class="sxs-lookup"><span data-stu-id="52962-133">Encrypting using an asymmetric key.</span></span>|[<span data-ttu-id="52962-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52962-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)|  
|<span data-ttu-id="52962-135">Chiffrement à l'aide d'un certificat.</span><span class="sxs-lookup"><span data-stu-id="52962-135">Encrypting using a certificate.</span></span>|[<span data-ttu-id="52962-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="52962-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)|  
|<span data-ttu-id="52962-137">Chiffrement de fichiers de base de données à l'aide du chiffrement transparent des données.</span><span class="sxs-lookup"><span data-stu-id="52962-137">Encrypting database files using transparent data encryption.</span></span>|[<span data-ttu-id="52962-138">Chiffrement transparent des données &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="52962-138">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)|  
|<span data-ttu-id="52962-139">Comment chiffrer une colonne d'une table.</span><span class="sxs-lookup"><span data-stu-id="52962-139">How to encrypt one column of a table.</span></span>|[<span data-ttu-id="52962-140">Chiffrer une colonne de données</span><span class="sxs-lookup"><span data-stu-id="52962-140">Encrypt a Column of Data</span></span>](encrypt-a-column-of-data.md)|  
  
## <a name="see-also"></a><span data-ttu-id="52962-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52962-141">See Also</span></span>  
 <span data-ttu-id="52962-142">[Chiffrement SQL Server](sql-server-encryption.md) </span><span class="sxs-lookup"><span data-stu-id="52962-142">[SQL Server Encryption](sql-server-encryption.md) </span></span>  
 [<span data-ttu-id="52962-143">Hiérarchie de chiffrement</span><span class="sxs-lookup"><span data-stu-id="52962-143">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
