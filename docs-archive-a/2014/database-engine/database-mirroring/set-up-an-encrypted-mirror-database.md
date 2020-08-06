---
title: Configurer une base de données miroir chiffrée | Microsoft Docs
ms.custom: ''
ms.date: 06/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], database mirroring
- encryption [SQL Server], database mirroring
- database master key [SQL Server], database mirroring
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 7329a575-be29-46e0-abc6-1344db37920c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a5148411792f1ea881bba59e599252284575bbdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701759"
---
# <a name="set-up-an-encrypted-mirror-database"></a><span data-ttu-id="17f67-102">Configurer une base de données miroir chiffrée</span><span class="sxs-lookup"><span data-stu-id="17f67-102">Set Up an Encrypted Mirror Database</span></span>

<span data-ttu-id="17f67-103">Pour activer le déchiffrement automatique de la clé principale d'une base de données miroir, vous devez fournir le mot de passe utilisé pour chiffrer la clé principale à l'instance de serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="17f67-103">To enable automatic decryption of the database master key of a mirror database, you must provide the password used to encrypt the master key to the mirror server instance.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="17f67-104">et les versions ultérieures incluent des mécanismes de transfert du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="17f67-104">and later versions include mechanisms to transfer the password.</span></span> <span data-ttu-id="17f67-105">Utilisez **sp_control_dbmasterkey_password** pour créer des informations d’identification destinées à la clé principale de la base de données avant de démarrer la mise en miroir de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="17f67-105">Use **sp_control_dbmasterkey_password** to create a credential for the database master key before you start database mirroring.</span></span> <span data-ttu-id="17f67-106">Vous devez répéter cette procédure pour chaque base de données qui sera mise en miroir.</span><span class="sxs-lookup"><span data-stu-id="17f67-106">You must repeat this process for every database that will be mirrored.</span></span> <span data-ttu-id="17f67-107">Pour plus d’informations, consultez [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17f67-107">For more information, see [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span></span>
  
> [!CAUTION]  
>  <span data-ttu-id="17f67-108">N’activez pas le déchiffrement avec basculement d’une base de données qui doit rester inaccessible à l’administrateur système ( **sa** ) et à d’autres principaux de serveur hautement privilégiés.</span><span class="sxs-lookup"><span data-stu-id="17f67-108">Do not enable failover decryption of a database that must remain inaccessible to **sa** and other highly privileged server principals.</span></span> <span data-ttu-id="17f67-109">Vous pouvez configurer une base de données de sorte que la hiérarchie de ses clés ne puisse pas être déchiffrée par la clé principale du service.</span><span class="sxs-lookup"><span data-stu-id="17f67-109">You can configure a database so that its key hierarchy cannot be decrypted by the service master key.</span></span> <span data-ttu-id="17f67-110">Cette option est prise en charge comme défense renforcée des bases de données contenant des informations qui ne doivent pas être accessibles à l’administrateur système ( **sa** ) ou à d’autres principaux de serveur hautement privilégiés.</span><span class="sxs-lookup"><span data-stu-id="17f67-110">This option is supported as a defense-in-depth for databases that contain information that should not be accessible to **sa** or other highly privileged server principals.</span></span> <span data-ttu-id="17f67-111">L’activation du déchiffrement avec basculement de cette base de données supprime cette défense renforcée, en permettant à l’administrateur système ( **sa** ) et à d’autres principaux de serveur hautement privilégiés de déchiffrer la base de données.</span><span class="sxs-lookup"><span data-stu-id="17f67-111">Enabling failover decryption of such a database removes this defense-in-depth, enabling **sa** and other highly privileged server principals to decrypt the database.</span></span>  


<!-- Note: We cannot append '?view=sql-server-2016' to these, even tho in theory we might want to. -->

## <a name="see-also"></a><span data-ttu-id="17f67-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17f67-112">See Also</span></span>

[<span data-ttu-id="17f67-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17f67-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql)

[<span data-ttu-id="17f67-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17f67-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)

[<span data-ttu-id="17f67-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17f67-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-master-key-transact-sql)

[<span data-ttu-id="17f67-116">Hiérarchie de chiffrement</span><span class="sxs-lookup"><span data-stu-id="17f67-116">Encryption Hierarchy</span></span>](../../relational-databases/security/encryption/encryption-hierarchy.md)

[<span data-ttu-id="17f67-117">Configuration de la mise en miroir d’une base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17f67-117">Setting Up Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)

