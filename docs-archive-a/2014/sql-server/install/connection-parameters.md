---
title: Paramètres de connexion | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], connections
- authentication [Upgrade Advisor]
- SQL Server Upgrade Advisor, connections
- connections [Upgrade Advisor]
- server instances [Upgrade Advisor]
- default server instances
- analyzing system [Upgrade Advisor], connections
ms.assetid: f754d038-637a-4d8e-85b0-b242e6499d26
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27eb69dfd2c41710a47861e0992486267f692a3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603233"
---
# <a name="connection-parameters"></a><span data-ttu-id="cae7d-102">Paramètres de connexion</span><span class="sxs-lookup"><span data-stu-id="cae7d-102">Connection Parameters</span></span>
  <span data-ttu-id="cae7d-103">Pour analyser certains types de serveurs, tels que [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , vous devez sélectionner une instance spécifique de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cae7d-103">To analyze certain server types, such as the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], you must select a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cae7d-104">L'instance par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est sélectionnée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="cae7d-104">The default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is automatically selected.</span></span> <span data-ttu-id="cae7d-105">Vous pouvez modifier cette sélection, mais vous ne pouvez choisir qu'une instance à la fois pour l'analyse par le Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cae7d-105">You can change this selection, but you can select only one instance at a time for analysis by Upgrade Advisor.</span></span> <span data-ttu-id="cae7d-106">Si vous avez inclus un type de serveur qui requiert une authentification, vous devez entrer le mode et les informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="cae7d-106">If you have included a server type that requires authentication, you must enter the authentication mode and credentials.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cae7d-107">Options</span><span class="sxs-lookup"><span data-stu-id="cae7d-107">Options</span></span>  
 <span data-ttu-id="cae7d-108">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="cae7d-108">**Server name**</span></span>  
 <span data-ttu-id="cae7d-109">Prérempli avec le nom d'ordinateur que vous avez entré dans le volet Composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae7d-109">Pre-populated with the computer name that you entered in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components pane.</span></span>  
  
 <span data-ttu-id="cae7d-110">**Nom de l’instance**</span><span class="sxs-lookup"><span data-stu-id="cae7d-110">**Instance name**</span></span>  
 <span data-ttu-id="cae7d-111">Choisissez parmi les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui sont disponibles sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cae7d-111">Select from the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are available on the computer.</span></span> <span data-ttu-id="cae7d-112">Si vous ne voyez pas de liste d’instances, utilisez MSSQLSERVER pour analyser l’instance par défaut.</span><span class="sxs-lookup"><span data-stu-id="cae7d-112">If you do not see a list of instances, use MSSQLSERVER to scan the default instance.</span></span> <span data-ttu-id="cae7d-113">Ceci s'applique particulièrement pour les ordinateurs distants.</span><span class="sxs-lookup"><span data-stu-id="cae7d-113">This is especially relevant for remote computers.</span></span> <span data-ttu-id="cae7d-114">Vous pouvez également utiliser le mot "default" pour rechercher l'instance par défaut.</span><span class="sxs-lookup"><span data-stu-id="cae7d-114">You can also use the word "default" to scan the default instance.</span></span>  
  
 <span data-ttu-id="cae7d-115">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="cae7d-115">**Authentication**</span></span>  
 <span data-ttu-id="cae7d-116">Sélectionnez un mode dans la liste des modes d'authentification disponibles sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cae7d-116">Select from the list of available authentication modes on this computer.</span></span> <span data-ttu-id="cae7d-117">Par défaut, le mode d'authentification correspond à l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="cae7d-117">By default, the authentication mode is Windows Authentication.</span></span>  
  
 <span data-ttu-id="cae7d-118">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="cae7d-118">**User name**</span></span>  
 <span data-ttu-id="cae7d-119">Si vous utilisez l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], entrez un nom d'utilisateur dans la zone.</span><span class="sxs-lookup"><span data-stu-id="cae7d-119">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, enter a user name in the box.</span></span> <span data-ttu-id="cae7d-120">Il est recommandé que le nom d'utilisateur ait des informations d'identification d'administration sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cae7d-120">We recommend that the user name have administrative credentials on the computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cae7d-121">Si vous sélectionnez l’authentification Windows, le nom d’utilisateur de l’utilisateur actuellement connecté est renseigné dans la zone de texte **nom d’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="cae7d-121">If you select Windows Authentication, the user name of the currently logged-on user is populated in the **User name** text box.</span></span>  
  
 <span data-ttu-id="cae7d-122">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="cae7d-122">**Password**</span></span>  
 <span data-ttu-id="cae7d-123">Entrez le mot de passe de l'utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="cae7d-123">Enter the password for the specified user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae7d-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cae7d-124">See Also</span></span>  
 <span data-ttu-id="cae7d-125">[Utilisation du conseiller de mise à niveau](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="cae7d-125">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="cae7d-126">Guide de référence de l'interface utilisateur du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cae7d-126">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
