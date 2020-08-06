---
title: MSSQLSERVER_50000 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 50000 [SQL Server Native Client setup error]
ms.assetid: 5426d87a-d5d9-4984-b211-b07d69e834a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cc805042bff7259a311ca3f2acf4c26db59381b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701214"
---
# <a name="mssqlserver_50000"></a><span data-ttu-id="d32d5-102">MSSQLSERVER_50000</span><span class="sxs-lookup"><span data-stu-id="d32d5-102">MSSQLSERVER_50000</span></span>
    
## <a name="details"></a><span data-ttu-id="d32d5-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d32d5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d32d5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d32d5-104">Product Name</span></span>|<span data-ttu-id="d32d5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d32d5-105">SQL Server</span></span>|  
|<span data-ttu-id="d32d5-106">Version du produit</span><span class="sxs-lookup"><span data-stu-id="d32d5-106">Product Version</span></span>|<span data-ttu-id="d32d5-107">11.0</span><span class="sxs-lookup"><span data-stu-id="d32d5-107">11.0</span></span>|  
|<span data-ttu-id="d32d5-108">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d32d5-108">Event ID</span></span>|<span data-ttu-id="d32d5-109">50000</span><span class="sxs-lookup"><span data-stu-id="d32d5-109">50000</span></span>|  
|<span data-ttu-id="d32d5-110">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d32d5-110">Event Source</span></span>|<span data-ttu-id="d32d5-111">SETUP</span><span class="sxs-lookup"><span data-stu-id="d32d5-111">SETUP</span></span>|  
|<span data-ttu-id="d32d5-112">Composant</span><span class="sxs-lookup"><span data-stu-id="d32d5-112">Component</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d32d5-113">Native Client</span><span class="sxs-lookup"><span data-stu-id="d32d5-113">Native Client</span></span>|  
|<span data-ttu-id="d32d5-114">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d32d5-114">Symbolic Name</span></span>||  
|<span data-ttu-id="d32d5-115">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d32d5-115">Message Text</span></span>|<span data-ttu-id="d32d5-116">Erreur réseau lors de la tentative de lecture du fichier : '%. \* ls'.</span><span class="sxs-lookup"><span data-stu-id="d32d5-116">A network error occurred while attempting to read from the file '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d32d5-117">Explication</span><span class="sxs-lookup"><span data-stu-id="d32d5-117">Explanation</span></span>  
 <span data-ttu-id="d32d5-118">Tentative d'installation (ou de mise à jour) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sur un ordinateur où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client est déjà installé, et où l'installation existante provenait d'un fichier MSI qui a été renommé de sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="d32d5-118">An attempt was made to install (or update) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client on a computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is already installed, and where the existing installation was from an MSI file that was renamed from sqlncli.msi.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d32d5-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d32d5-119">User Action</span></span>  
 <span data-ttu-id="d32d5-120">Pour résoudre cette erreur, désinstallez la version existante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d32d5-120">To resolve this error, uninstall the existing version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="d32d5-121">Pour empêcher cette erreur, n'installez pas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client à partir d'un fichier MSI qui n'est pas nommé sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="d32d5-121">To prevent this error, do not install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client from an MSI file that is not named sqlncli.msi.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="d32d5-122">Interne uniquement</span><span class="sxs-lookup"><span data-stu-id="d32d5-122">Internal-Only</span></span>  
  
