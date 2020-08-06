---
title: Suivre les étapes consécutives à l’installation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 0a788a2a-9b4f-4bfc-b1b5-83eeb1ea9ab2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1e9aae3dccaa409bcebc473213286f3edf19e7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610911"
---
# <a name="complete-the-post-installation-steps"></a><span data-ttu-id="c4cc5-102">Suivre les étapes consécutives à l'installation</span><span class="sxs-lookup"><span data-stu-id="c4cc5-102">Complete the Post-Installation Steps</span></span>
  <span data-ttu-id="c4cc5-103">Après avoir installé Distributed Replay, vous devez modifier le compte de contrôleur Distributed Replay et les comptes de services clients.</span><span class="sxs-lookup"><span data-stu-id="c4cc5-103">After you install Distributed Replay you must modify the Distributed Replay controller and client services accounts.</span></span>  
  
### <a name="to-complete-the-post-installation-steps"></a><span data-ttu-id="c4cc5-104">Pour suivre les étapes consécutives à l'installation</span><span class="sxs-lookup"><span data-stu-id="c4cc5-104">To complete the post-installation steps</span></span>  
  
1.  <span data-ttu-id="c4cc5-105">**Créez des règles de pare-feu** : Sur les ordinateurs contrôleurs et clients, vous devez autoriser le trafic entrant à travers le pare-feu pour le service correspondant.</span><span class="sxs-lookup"><span data-stu-id="c4cc5-105">**Create firewall rules**: On the controller and client computers, you must allow inbound traffic through the firewall for the corresponding service.</span></span> <span data-ttu-id="c4cc5-106">Spécifiez des règles de pare-feu pour les exécutables du service, situés dans les dossiers d'installation.</span><span class="sxs-lookup"><span data-stu-id="c4cc5-106">Specify the firewall rules for the service executables, located in the installation folders.</span></span>  
  
    1.  <span data-ttu-id="c4cc5-107">Pour le service contrôleur, créez une règle pour **DReplayController.exe**, situé dans le dossier d’installation.</span><span class="sxs-lookup"><span data-stu-id="c4cc5-107">For the controller service, create a rule for **DReplayController.exe**, located in the installation folder.</span></span> <span data-ttu-id="c4cc5-108">Par exemple, la commande suivante active cette règle, sachant que `%InstallPath%` est le dossier d'installation du service :</span><span class="sxs-lookup"><span data-stu-id="c4cc5-108">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay controller" dir=in program="%InstallPath%\DReplayController\DReplayController.exe" action=allow`  
  
    2.  <span data-ttu-id="c4cc5-109">Pour le service client, sur chaque ordinateur client, créez une règle pour **DReplayClient.exe**, situé dans le dossier d’installation.</span><span class="sxs-lookup"><span data-stu-id="c4cc5-109">For the client service, on each client computer, create a rule for **DReplayClient.exe**, located in the installation folder.</span></span> <span data-ttu-id="c4cc5-110">Par exemple, la commande suivante active cette règle, sachant que `%InstallPath%` est le dossier d'installation du service :</span><span class="sxs-lookup"><span data-stu-id="c4cc5-110">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay client" dir=in program="%InstallPath%\DReplayClient\DReplayClient.exe" action=allow`  
  
2.  <span data-ttu-id="c4cc5-111">**Accorder à chaque client des autorisations sur le serveur cible** : Après avoir achevé l’installation du service client sur les ordinateurs clients, vous devez ajouter manuellement les comptes de services clients au rôle sysadmin sur l’instance cible de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4cc5-111">**Grant each client permissions on the target server**: After you have completed installing the client service on the client computers, you must manually add the client service accounts to the sysadmin role on the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c4cc5-112">Sécurité du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c4cc5-112">.NET Framework Security</span></span>  
 <span data-ttu-id="c4cc5-113">Vous devez posséder des autorisations administratives pour installer les fonctionnalités de Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="c4cc5-113">You must have administrative permissions in order to install any of the Distributed Replay features.</span></span> <span data-ttu-id="c4cc5-114">Seule une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disposant d’autorisations sysadmin peut ajouter des comptes de services clients au rôle serveur sysadmin du serveur de test.</span><span class="sxs-lookup"><span data-stu-id="c4cc5-114">Only a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login having sysadmin permissions can add the client service accounts to the sysadmin server role of the test server.</span></span> <span data-ttu-id="c4cc5-115">Pour plus d'informations sur les questions de sécurité de Distributed Replay, consultez [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="c4cc5-115">For more information about Distributed Replay security considerations, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
  
