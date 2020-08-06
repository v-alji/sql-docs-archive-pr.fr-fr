---
title: Sélectionner un package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.selectapackage.f1
helpviewer_keywords:
- Select a Package dialog box
ms.assetid: 92b47a2b-21b5-460a-885d-6cc4bb567249
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b35276791b004a011a1c2656057046be05ed6770
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600177"
---
# <a name="select-a-package"></a><span data-ttu-id="cb5eb-102">Sélectionner un package</span><span class="sxs-lookup"><span data-stu-id="cb5eb-102">Select a Package</span></span>
  <span data-ttu-id="cb5eb-103">Utilisez la boîte de dialogue **Sélectionner un package** pour spécifier le package à partir duquel la tâche MSMQ peut recevoir des messages.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-103">Use the **Select a Package** dialog box to specify the package from which the Message Queue task can receive messages.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="cb5eb-104">Options statiques</span><span class="sxs-lookup"><span data-stu-id="cb5eb-104">Static Options</span></span>  
 <span data-ttu-id="cb5eb-105">**Lieu**</span><span class="sxs-lookup"><span data-stu-id="cb5eb-105">**Location**</span></span>  
 <span data-ttu-id="cb5eb-106">Spécifiez l'emplacement du package.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-106">Specify the location of the package.</span></span> <span data-ttu-id="cb5eb-107">Cette propriété dispose des options répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-107">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="cb5eb-108">Valeur</span><span class="sxs-lookup"><span data-stu-id="cb5eb-108">Value</span></span>|<span data-ttu-id="cb5eb-109">Description</span><span class="sxs-lookup"><span data-stu-id="cb5eb-109">Description</span></span>|  
|-----------|-----------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<span data-ttu-id="cb5eb-110">Définissez l'emplacement d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb5eb-110">Set the location to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cb5eb-111">La sélection de cette valeur affiche les options dynamiques, **Serveur**, **Utiliser l'authentification Windows**, **Utiliser l'authentification SQL Server**, **Nom d'utilisateur**et **Mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-111">Selecting this value displays the dynamic options, **Server**, **Use Windows Authentication**, **Use SQL Server Authentication**, **User name**, and **Password**.</span></span>|  
|<span data-ttu-id="cb5eb-112">Fichier DTSX</span><span class="sxs-lookup"><span data-stu-id="cb5eb-112">DTSX file</span></span>|<span data-ttu-id="cb5eb-113">Définissez l'emplacement d'un fichier DTSX.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-113">Set the location to a DTSX file.</span></span> <span data-ttu-id="cb5eb-114">La sélection de cette valeur affiche l'option dynamique **Nom de fichier**.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-114">Selecting this value displays the dynamic option, **File name**.</span></span>|  
  
## <a name="location-dynamic-options"></a><span data-ttu-id="cb5eb-115">Options dynamiques pour la définition de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="cb5eb-115">Location Dynamic Options</span></span>  
  
### <a name="location--sql-server"></a><span data-ttu-id="cb5eb-116">Emplacement = SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb5eb-116">Location = SQL Server</span></span>  
 <span data-ttu-id="cb5eb-117">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="cb5eb-117">**Package name**</span></span>  
 <span data-ttu-id="cb5eb-118">Sélectionnez un package stocké sur le serveur spécifié.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-118">Select a package that is stored on the specified server.</span></span>  
  
 <span data-ttu-id="cb5eb-119">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="cb5eb-119">**Server**</span></span>  
 <span data-ttu-id="cb5eb-120">Tapez le nom d'un serveur ou sélectionnez-en un dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-120">Provide a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="cb5eb-121">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="cb5eb-121">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="cb5eb-122">Cliquez pour utiliser l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-122">Click to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="cb5eb-123">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="cb5eb-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="cb5eb-124">Cliquez pour utiliser l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb5eb-124">Click to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="cb5eb-125">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="cb5eb-125">**User name**</span></span>  
 <span data-ttu-id="cb5eb-126">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , fournissez un nom d’utilisateur à utiliser pour ouvrir une session sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-126">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a user name to use when logging on to the server.</span></span>  
  
 <span data-ttu-id="cb5eb-127">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="cb5eb-127">**Password**</span></span>  
 <span data-ttu-id="cb5eb-128">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , entrez un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-128">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
### <a name="location--dtsx-file"></a><span data-ttu-id="cb5eb-129">Emplacement = Fichier DTSX</span><span class="sxs-lookup"><span data-stu-id="cb5eb-129">Location = DTSX file</span></span>  
 <span data-ttu-id="cb5eb-130">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="cb5eb-130">**File name**</span></span>  
 <span data-ttu-id="cb5eb-131">Indiquez le chemin d’un package ou cliquez sur le bouton Parcourir **(...)** pour rechercher le package.</span><span class="sxs-lookup"><span data-stu-id="cb5eb-131">Provide the path of a package or click the browse button **(...)** and locate the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb5eb-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb5eb-132">See Also</span></span>  
 [<span data-ttu-id="cb5eb-133">Tâche MSMQ</span><span class="sxs-lookup"><span data-stu-id="cb5eb-133">Message Queue Task</span></span>](message-queue-task.md)  
  
  
