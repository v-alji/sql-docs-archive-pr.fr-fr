---
title: Définir des options de chiffrement sur des serveurs cibles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, encryption
- target servers [SQL Server], encryption
- multiserver environments [SQL Server], setting encryption options on target servers
ms.assetid: 1a9fd539-e166-4ea8-9f21-ac400ca74dee
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd10d2e05e59015542f41cc123de993e6128f9f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613274"
---
# <a name="set-encryption-options-on-target-servers"></a><span data-ttu-id="31e21-102">Définir des options de chiffrement sur des serveurs cibles</span><span class="sxs-lookup"><span data-stu-id="31e21-102">Set Encryption Options on Target Servers</span></span>
  <span data-ttu-id="31e21-103">Si vous ne pouvez pas utiliser de certificat pour les communications chiffrées SSL (Secure Sockets Layer) entre des serveurs maîtres et tous ou une partie de vos serveurs cibles, mais que vous souhaitez chiffrer le canal entre ces serveurs, configurez le serveur cible de façon à utiliser le niveau de sécurité requis.</span><span class="sxs-lookup"><span data-stu-id="31e21-103">If you cannot use a certificate for Secure Sockets Layer (SSL) encrypted communications between master servers and some or all of your target servers, but you want to encrypt the channel between them, configure the target server to use the level of security required.</span></span>  
  
 <span data-ttu-id="31e21-104">Pour configurer le niveau de sécurité approprié requis pour un canal de communication serveur maître/serveur cible spécifique, définissez la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sous-clé de registre de l’agent \*\*\ HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Microsoft SQL Server \\ \*\* \<*instance_name*> **\SQLServerAgent\MsxEncryptChannelOptions (REG_DWORD)** sur le serveur cible sur l’une des valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="31e21-104">To configure the appropriate level of security required for a specific master server/target server communication channel, set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\**\<*instance_name*>**\SQLServerAgent\MsxEncryptChannelOptions(REG_DWORD)** on the target server to one of the following values.</span></span> <span data-ttu-id="31e21-105">La valeur de \<*instance_name*> est **MSSQL.** _n_.</span><span class="sxs-lookup"><span data-stu-id="31e21-105">The value of \<*instance_name*> is **MSSQL.**_n_.</span></span> <span data-ttu-id="31e21-106">Par exemple, **MSSQL.1** ou **MSSQL.3**.</span><span class="sxs-lookup"><span data-stu-id="31e21-106">For example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
|<span data-ttu-id="31e21-107">Valeur</span><span class="sxs-lookup"><span data-stu-id="31e21-107">Value</span></span>|<span data-ttu-id="31e21-108">Description</span><span class="sxs-lookup"><span data-stu-id="31e21-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="31e21-109">**0**</span><span class="sxs-lookup"><span data-stu-id="31e21-109">**0**</span></span>|<span data-ttu-id="31e21-110">Désactive le chiffrement entre ce serveur cible et le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="31e21-110">Disables encryption between this target server and the master server.</span></span> <span data-ttu-id="31e21-111">Ne choisissez cette option que lorsque le canal entre le serveur cible et le serveur maître est sécurisé par d'autres moyens.</span><span class="sxs-lookup"><span data-stu-id="31e21-111">Choose this option only when the channel between the target server and master server is secured by another means.</span></span>|  
|<span data-ttu-id="31e21-112">**1**</span><span class="sxs-lookup"><span data-stu-id="31e21-112">**1**</span></span>|<span data-ttu-id="31e21-113">Active le chiffrement uniquement entre ce serveur cible et le serveur maître, mais aucune validation de certificat n'est requise.</span><span class="sxs-lookup"><span data-stu-id="31e21-113">Enables encryption only between this target server and the master server, but no certificate validation is required.</span></span>|  
|<span data-ttu-id="31e21-114">**2**</span><span class="sxs-lookup"><span data-stu-id="31e21-114">**2**</span></span>|<span data-ttu-id="31e21-115">Active le chiffrement SSL et la validation de certificat complets entre ce serveur cible et le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="31e21-115">Enables full SSL encryption and certificate validation between this target server and the master server.</span></span> <span data-ttu-id="31e21-116">Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="31e21-116">This setting is the default.</span></span> <span data-ttu-id="31e21-117">Sauf si vous avez une raison particulière de choisir une valeur différente, nous vous recommandons de ne pas le modifier.</span><span class="sxs-lookup"><span data-stu-id="31e21-117">Unless you have specific reason to choose a different value, we recommend not changing it.</span></span>|  
  
 <span data-ttu-id="31e21-118">Si **1** ou **2** est spécifié, le protocole SSL doit être activé sur les serveurs maîtres et cibles.</span><span class="sxs-lookup"><span data-stu-id="31e21-118">If **1** or **2** is specified, you must have SSL enabled on both the master and target servers.</span></span> <span data-ttu-id="31e21-119">Si **2** est spécifié, un certificat signé correctement doit également être présent sur le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="31e21-119">If **2** is specified, you must also have a properly signed certificate present on the master server.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31e21-120"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31e21-120">See Also</span></span>  
 [<span data-ttu-id="31e21-121">Activer les connexions chiffrées dans le moteur de base de données &#40;Gestionnaire de configuration SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="31e21-121">Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;</span></span>](../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md)  
  
  
