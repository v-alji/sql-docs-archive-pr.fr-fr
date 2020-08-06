---
title: Créer un rôle défini par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c4128993-2333-48c7-84b1-e51cdcea393d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0ee905c2636e20315c2180a6be8f8e40f76d5f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604062"
---
# <a name="create-a-user-defined-role"></a><span data-ttu-id="d31e3-102">Créer un rôle défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d31e3-102">Create a User-Defined Role</span></span>
    
### <a name="to-create-a-user-defined-role"></a><span data-ttu-id="d31e3-103">Pour créer un rôle défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d31e3-103">To create a user-defined role</span></span>  
  
1.  <span data-ttu-id="d31e3-104">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d31e3-104">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="d31e3-105">Cliquez sur **Explorateur d'objets** dans le menu **Affichage** .</span><span class="sxs-lookup"><span data-stu-id="d31e3-105">Click **Object Explorer** on the **View** menu.</span></span>  
  
3.  <span data-ttu-id="d31e3-106">Dans la barre d'outils de l'Explorateur d'objets, cliquez sur **Connecter**, puis sur **Moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="d31e3-106">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
4.  <span data-ttu-id="d31e3-107">Dans la boîte de dialogue **Se connecter au serveur** , entrez un nom de serveur et sélectionnez un mode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="d31e3-107">In the **Connect to Server** dialog box, provide a server name and select an authentication mode.</span></span> <span data-ttu-id="d31e3-108">Vous pouvez utiliser un point ( . ), (local) ou `localhost` pour indiquer le serveur local.</span><span class="sxs-lookup"><span data-stu-id="d31e3-108">You can use a period (.), (local), or `localhost` to indicate the local server.</span></span>  
  
5.  <span data-ttu-id="d31e3-109">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="d31e3-109">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="d31e3-110">Développez Bases de données, Bases de données système, msdb, Sécurité et Rôles.</span><span class="sxs-lookup"><span data-stu-id="d31e3-110">Expand Databases, System Databases, msdb, Security, and Roles.</span></span>  
  
7.  <span data-ttu-id="d31e3-111">Dans le nœud Rôles, cliquez avec le bouton droit sur Rôles de base de données, puis cliquez sur **Nouveau rôle de base de données**.</span><span class="sxs-lookup"><span data-stu-id="d31e3-111">In the Roles node, right-click Database Roles, and click **New Database Role**.</span></span>  
  
8.  <span data-ttu-id="d31e3-112">Sur la page Général, entrez un nom, et, si vous le souhaitez, spécifiez un propriétaire et des schémas appartenant à un rôle et ajoutez des membres de rôle.</span><span class="sxs-lookup"><span data-stu-id="d31e3-112">On the General page, provide a name and optionally, specify an owner and owned schemas and add role members.</span></span>  
  
9. <span data-ttu-id="d31e3-113">Vous pouvez également cliquer sur **Autorisations** pour configurer les autorisations pour les objets.</span><span class="sxs-lookup"><span data-stu-id="d31e3-113">Optionally, click **Permissions** and configure object permissions.</span></span>  
  
10. <span data-ttu-id="d31e3-114">Vous pouvez également cliquer sur **Propriétés étendues** pour configurer les éventuelles propriétés étendues.</span><span class="sxs-lookup"><span data-stu-id="d31e3-114">Optionally, click **Extended Properties** and configure any extended properties.</span></span>  
  
11. <span data-ttu-id="d31e3-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d31e3-115">Click **OK**.</span></span>  
  
  
