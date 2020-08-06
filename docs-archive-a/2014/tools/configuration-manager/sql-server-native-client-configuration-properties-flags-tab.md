---
title: Propriétés de la configuration de SQL Server Native Client (onglet Indicateurs) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 59af121d-c8b9-4faa-91a1-b664f2c9b441
author: stevestein
ms.author: sstein
ms.openlocfilehash: b3ca7b87963fc3848bbb933a5c21f9d608d37d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613707"
---
# <a name="sql-server-native-client-configuration-properties-flags-tab"></a><span data-ttu-id="df363-102">Propriétés de la configuration de SQL Server Native Client (onglet Indicateurs)</span><span class="sxs-lookup"><span data-stu-id="df363-102">SQL Server Native Client Configuration Properties (Flags Tab)</span></span>
  <span data-ttu-id="df363-103">Les clients [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installés sur cet ordinateur communiquent avec les serveurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant les protocoles fournis dans le fichier de bibliothèque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="df363-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this machine, communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers using the protocols provided in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client library file.</span></span> <span data-ttu-id="df363-104">Cette page permet de configurer l'ordinateur client de manière à ce qu'il demande une connexion chiffrée utilisant le protocole SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="df363-104">This page provides configures the client computer to request an encrypted connection using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="df363-105">En cas d'impossibilité d'établir une connexion chiffrée, la connexion échoue.</span><span class="sxs-lookup"><span data-stu-id="df363-105">If an encrypted connection cannot be established, the connection will fail.</span></span>  
  
 <span data-ttu-id="df363-106">Le processus de connexion est toujours chiffré.</span><span class="sxs-lookup"><span data-stu-id="df363-106">The login process is always encrypted.</span></span> <span data-ttu-id="df363-107">Les options ci-dessous s'appliquent uniquement aux données de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="df363-107">The options below apply only to encrypting data.</span></span> <span data-ttu-id="df363-108">Pour plus d’informations sur la manière dont [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] chiffre les communications et pour obtenir des instructions sur la manière de configurer le client pour qu’il approuve l’autorité racine du certificat du serveur, consultez « Chiffrement des connexions à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]» et « Activer les connexions chiffrées dans le [!INCLUDE[ssDE](../../includes/ssde-md.md)] (Gestionnaire de configuration[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) » dans la documentation en ligne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df363-108">For more information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encrypts communication and for instructions on how to configure the client to trust the root authority of the server certificate, see "Encrypting Connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" and "How to: Enable Encrypted Connections to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="df363-109">Options</span><span class="sxs-lookup"><span data-stu-id="df363-109">Options</span></span>  
 <span data-ttu-id="df363-110">**Forcer le chiffrement du protocole**</span><span class="sxs-lookup"><span data-stu-id="df363-110">**Force protocol encryption**</span></span>  
 <span data-ttu-id="df363-111">Demande une connexion utilisant le protocole SSL.</span><span class="sxs-lookup"><span data-stu-id="df363-111">Request a connection using SSL.</span></span>  
  
 <span data-ttu-id="df363-112">**Faire confiance au certificat de serveur**</span><span class="sxs-lookup"><span data-stu-id="df363-112">**Trust Server Certificate**</span></span>  
 <span data-ttu-id="df363-113">Quand cette option a la valeur **Non**, le processus client tente de valider le certificat du serveur.</span><span class="sxs-lookup"><span data-stu-id="df363-113">When set to **No**, the client process attempts to validate the server certificate.</span></span> <span data-ttu-id="df363-114">Le client et le serveur doivent tous les deux posséder un certificat émanant d'une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="df363-114">The client and server must have each have a certificate issues from a public certification authority.</span></span> <span data-ttu-id="df363-115">Si le certificat n'est pas présent sur l'ordinateur client ou que la validation du certificat échoue, la connexion prend fin.</span><span class="sxs-lookup"><span data-stu-id="df363-115">If the certificate is not present on the client computer, or if the validation of the certificate fails, the connection is terminated.</span></span>  
  
 <span data-ttu-id="df363-116">Quand l’option a la valeur **Oui**, le client ne valide pas le certificat du serveur, ce qui permet d’utiliser un certificat autosigné.</span><span class="sxs-lookup"><span data-stu-id="df363-116">When set to **Yes**, the client does not validate the server certificate, thereby enabling the use of a self-signed certificate.</span></span>  
  
 <span data-ttu-id="df363-117">**Faire confiance au certificat de serveur** n’est disponible que si l’option **Forcer le chiffrement du protocole** a la valeur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="df363-117">**Trust Server Certificate** is only available if **Force protocol encryption** is set to **Yes**.</span></span>  
  
  
