---
title: LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: fa082dca-bf88-46e7-b61e-7ac8835a3493
author: stevestein
ms.author: sstein
ms.openlocfilehash: e71f7b443a1999a5edbb17dc11ee4d578834faf4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611081"
---
# <a name="localdb_error_unknown_language_id"></a><span data-ttu-id="9db5f-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="9db5f-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>
    
## <a name="details"></a><span data-ttu-id="9db5f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9db5f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9db5f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9db5f-104">Product Name</span></span>|<span data-ttu-id="9db5f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9db5f-105">SQL Server</span></span>|  
|<span data-ttu-id="9db5f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9db5f-106">Event ID</span></span>|<span data-ttu-id="9db5f-107">270</span><span class="sxs-lookup"><span data-stu-id="9db5f-107">270</span></span>|  
|<span data-ttu-id="9db5f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9db5f-108">Event Source</span></span>|<span data-ttu-id="9db5f-109">Runtime de base de données locale SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="9db5f-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="9db5f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9db5f-110">Component</span></span>|<span data-ttu-id="9db5f-111">API d'exécution de la base de données locale</span><span class="sxs-lookup"><span data-stu-id="9db5f-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="9db5f-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9db5f-112">Message Text</span></span>|<span data-ttu-id="9db5f-113">Erreur de réception du message d'erreur localisé.</span><span class="sxs-lookup"><span data-stu-id="9db5f-113">Error getting the localized error message.</span></span> <span data-ttu-id="9db5f-114">La langue spécifiée par le paramètre 'ID de langue' est inconnue.</span><span class="sxs-lookup"><span data-stu-id="9db5f-114">The language specified by 'Language ID' parameter is unknown.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9db5f-115">Explication</span><span class="sxs-lookup"><span data-stu-id="9db5f-115">Explanation</span></span>  
 <span data-ttu-id="9db5f-116">La langue demandée pour le message d'erreur d'exécution de base de données locale est inconnue ou non prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9db5f-116">The requested language for the Local Database Runtime error message is unknown or not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9db5f-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9db5f-117">User Action</span></span>  
 <span data-ttu-id="9db5f-118">Tentez de demander une langue prise en charge pour les messages d'erreur d'exécution de base de données locale, ou la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="9db5f-118">Try requesting one of the supported languages for Local Database Runtime error messages, or a default language.</span></span>  
  
  
