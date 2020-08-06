---
title: MSSQLSERVER_21862 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b945350d9c7a862d4274f464afbd7fc5472f732c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699671"
---
# <a name="mssqlserver_21862"></a><span data-ttu-id="7b547-102">MSSQLSERVER_21862</span><span class="sxs-lookup"><span data-stu-id="7b547-102">MSSQLSERVER_21862</span></span>
    
## <a name="details"></a><span data-ttu-id="7b547-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7b547-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b547-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7b547-104">Product Name</span></span>|<span data-ttu-id="7b547-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7b547-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7b547-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7b547-106">Event ID</span></span>|<span data-ttu-id="7b547-107">21862</span><span class="sxs-lookup"><span data-stu-id="7b547-107">21862</span></span>|  
|<span data-ttu-id="7b547-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7b547-108">Event Source</span></span>|<span data-ttu-id="7b547-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7b547-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7b547-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7b547-110">Component</span></span>|<span data-ttu-id="7b547-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7b547-111">SQLEngine</span></span>|  
|<span data-ttu-id="7b547-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7b547-112">Symbolic Name</span></span>|<span data-ttu-id="7b547-113">SQLErrorNum21862</span><span class="sxs-lookup"><span data-stu-id="7b547-113">SQLErrorNum21862</span></span>|  
|<span data-ttu-id="7b547-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7b547-114">Message Text</span></span>|<span data-ttu-id="7b547-115">Les colonnes FILESTREAM ne peuvent pas être publiées dans une publication à l'aide d'une méthode de synchronisation 'database snapshot' ou 'database snapshot character'.</span><span class="sxs-lookup"><span data-stu-id="7b547-115">FILESTREAM columns cannot be published in a publication by using a synchronization method of either 'database snapshot' or 'database snapshot character'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7b547-116">Explication</span><span class="sxs-lookup"><span data-stu-id="7b547-116">Explanation</span></span>  
 <span data-ttu-id="7b547-117">Étant donné qu’il est impossible d’accéder aux données FILESTREAM par le biais d’un instantané de base de données, l’agent d’instantané ne peut pas lire les données FILESTREAM quand le paramètre *database snapshot* ou *database_snapshot_character* est spécifié pour la méthode de synchronisation de la publication.</span><span class="sxs-lookup"><span data-stu-id="7b547-117">Because FILESTREAM data cannot be accessed through a database snapshot, the snapshot agent will be unable to read FILESTREAM data when either the *database snapshot* or *database_snapshot_character* parameter is specified for the synchronization method of the publication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7b547-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7b547-118">User Action</span></span>  
 <span data-ttu-id="7b547-119">Modifiez la méthode de synchronisation de publication en sélectionnant un paramètre autre que *database snapshot* ou *database_snapshot_character*, ou excluez simplement la colonne FILESTREAM de la publication.</span><span class="sxs-lookup"><span data-stu-id="7b547-119">Change the publication synchronization method to something other than *database snapshot* or *database_snapshot_character*, or just exclude the FILESTREAM column from the publication.</span></span>  
  
  
