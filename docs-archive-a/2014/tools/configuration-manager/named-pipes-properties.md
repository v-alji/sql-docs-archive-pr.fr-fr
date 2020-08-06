---
title: Propriétés des canaux nommés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server]
- listening [SQL Server], pipes
- pipes [SQL Server], listening on pipes
- Named Pipes [SQL Server], listening on pipes
ms.assetid: a5fd5b8e-f889-485b-89e3-d4010ec4c6ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80790c1cb8830a0fd132721f375a70d2574421b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604786"
---
# <a name="named-pipes-properties"></a><span data-ttu-id="e5f77-102">Propriétés de Canaux nommés</span><span class="sxs-lookup"><span data-stu-id="e5f77-102">Named Pipes Properties</span></span>
  <span data-ttu-id="e5f77-103">Utilisez la page **Protocole** de la boîte de dialogue **Propriétés des canaux nommés** pour afficher ou modifier le canal nommé sur lequel [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] écoute, pendant l’utilisation du protocole Canaux nommés.</span><span class="sxs-lookup"><span data-stu-id="e5f77-103">Use the **Protocol**page on the **Named Pipes Properties** dialog box to view or change the named pipe that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens to, when using the Named Pipes protocol.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e5f77-104">Pour activer ou désactiver le protocole, ou modifier le canal nommé, doit être redémarré.</span><span class="sxs-lookup"><span data-stu-id="e5f77-104">must be restarted to enable or disable the protocol, or change the named pipe.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e5f77-105">Options</span><span class="sxs-lookup"><span data-stu-id="e5f77-105">Options</span></span>  
 <span data-ttu-id="e5f77-106">**Activé**</span><span class="sxs-lookup"><span data-stu-id="e5f77-106">**Enabled**</span></span>  
 <span data-ttu-id="e5f77-107">Les valeurs possibles sont **Yes** et **No**.</span><span class="sxs-lookup"><span data-stu-id="e5f77-107">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="e5f77-108">**Nom du canal**</span><span class="sxs-lookup"><span data-stu-id="e5f77-108">**Pipe Name**</span></span>  
 <span data-ttu-id="e5f77-109">Spécifie le canal nommé sur lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] écoute.</span><span class="sxs-lookup"><span data-stu-id="e5f77-109">Specifies the named pipe on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens.</span></span> <span data-ttu-id="e5f77-110">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est à l'écoute sur `\\.\pipe\sql\query` pour l'instance par défaut et sur `\\.\pipe\MSSQL$<instancename>\sql\query` pour une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="e5f77-110">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query` for the default instance and `\\.\pipe\MSSQL$<instancename>\sql\query` for a named instance.</span></span> <span data-ttu-id="e5f77-111">Ce champ est limité à 2 047 caractères.</span><span class="sxs-lookup"><span data-stu-id="e5f77-111">This field is limited to 2047 characters.</span></span>  
  
## <a name="creating-an-alternate-named-pipe"></a><span data-ttu-id="e5f77-112">Création d'un autre canal nommé</span><span class="sxs-lookup"><span data-stu-id="e5f77-112">Creating an Alternate Named Pipe</span></span>  
 <span data-ttu-id="e5f77-113">Pour modifier le canal nommé, tapez le nom du nouveau canal dans la zone **Nom du canal** puis arrêtez et redémarrez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5f77-113">To change the named pipe, type the new pipe name in the **Pipe Name** box and then stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e5f77-114">Étant donné que **sql\query** est connu comme étant le canal nommé utilisé par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le fait de modifier ce canal peut permettre de réduire les risques d’attaques par des programmes malveillants.</span><span class="sxs-lookup"><span data-stu-id="e5f77-114">Since **sql\query** is well known as the named pipe used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], changing the pipe can help reduce the risk of attack by malicious programs.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e5f77-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="e5f77-115">Example</span></span>  
 <span data-ttu-id="e5f77-116">Tapez **\\\\.\pipe\unit\app** pour écouter sur le canal **unit\app** .</span><span class="sxs-lookup"><span data-stu-id="e5f77-116">Type **\\\\.\pipe\unit\app** to listen on the **unit\app** pipe.</span></span>  
  
 <span data-ttu-id="e5f77-117">Tapez **\\\\.\pipe\acct** pour écouter sur le canal **acct** .</span><span class="sxs-lookup"><span data-stu-id="e5f77-117">Type **\\\\.\pipe\acct** to listen on the **acct** pipe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f77-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5f77-118">See Also</span></span>  
 <span data-ttu-id="e5f77-119">[Activer ou désactiver un protocole réseau de serveur](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="e5f77-119">[Enable or Disable a Server Network Protocol](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 <span data-ttu-id="e5f77-120">[Choix d'un protocole réseau](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="e5f77-120">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="e5f77-121">Création d’une chaîne de connexion valide avec des canaux nommés</span><span class="sxs-lookup"><span data-stu-id="e5f77-121">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
