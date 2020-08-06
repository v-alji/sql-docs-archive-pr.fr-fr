---
title: Propriétés de SQL Server Agent (page Connexion) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.connection.f1
ms.assetid: d6a677ff-60ad-47ba-a0cb-df4193b165e0
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec9ae575f1ced510d95256d6827435e5b6ad89d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613263"
---
# <a name="sql-server-agent-properties-connection-page"></a><span data-ttu-id="b4754-102">Propriétés de l'Agent SQL Server (page Connexion)</span><span class="sxs-lookup"><span data-stu-id="b4754-102">SQL Server Agent Properties (Connection Page)</span></span>
  <span data-ttu-id="b4754-103">Utilisez cette page pour afficher et modifier les paramètres de la connexion du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service agent à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4754-103">Use this page to view and modify the settings for the connection from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="b4754-104">Options</span><span class="sxs-lookup"><span data-stu-id="b4754-104">Options</span></span>  
 <span data-ttu-id="b4754-105">**Alias du serveur hôte local**</span><span class="sxs-lookup"><span data-stu-id="b4754-105">**Alias local host server**</span></span>  
 <span data-ttu-id="b4754-106">Spécifie l'alias à utiliser pour se connecter à l'instance locale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4754-106">Specifies the alias to use to connect to the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b4754-107">Si vous ne pouvez pas utiliser les options de connexion par défaut pour l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , définissez un alias pour l'instance et spécifiez l'alias à cet endroit.</span><span class="sxs-lookup"><span data-stu-id="b4754-107">If you cannot use the default connection options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, define an alias for the instance and specify the alias here.</span></span>  
  
 <span data-ttu-id="b4754-108">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="b4754-108">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="b4754-109">Définit l'authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows comme la méthode d'authentification utilisée pour se connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4754-109">Sets [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b4754-110">se connecte sous le compte utilisé par le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="b4754-110">Agent connects as the account that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service runs as.</span></span>  
  
 <span data-ttu-id="b4754-111">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b4754-111">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="b4754-112">Définit l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comme la méthode d'authentification utilisée pour se connecter à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4754-112">Sets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b4754-113">est fournie dans un souci de compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="b4754-113">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="b4754-114">Pour une sécurité renforcée, utilisez l'authentification Windows dans la mesure du possible.</span><span class="sxs-lookup"><span data-stu-id="b4754-114">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="b4754-115">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="b4754-115">**Login**</span></span>  
 <span data-ttu-id="b4754-116">Permet de spécifier le nom d’accès à utiliser pour la connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4754-116">Specifies the login name to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b4754-117">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b4754-117">**Password**</span></span>  
 <span data-ttu-id="b4754-118">Permet de spécifier le mot de passe à utiliser pour la connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4754-118">Specifies the password to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
