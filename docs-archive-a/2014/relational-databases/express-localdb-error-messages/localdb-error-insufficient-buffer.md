---
title: LOCALDB_ERROR_INSUFFICIENT_BUFFER | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: ff67bda8-7e5c-4b06-8d7b-9985b6059a98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 934683cfca1a9a9c0596071824c21a0045e6ebab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614084"
---
# <a name="localdb_error_insufficient_buffer"></a><span data-ttu-id="22c35-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="22c35-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>
    
## <a name="details"></a><span data-ttu-id="22c35-103">Détails</span><span class="sxs-lookup"><span data-stu-id="22c35-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22c35-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="22c35-104">Product Name</span></span>|<span data-ttu-id="22c35-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="22c35-105">SQL Server</span></span>|  
|<span data-ttu-id="22c35-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="22c35-106">Event ID</span></span>|<span data-ttu-id="22c35-107">276</span><span class="sxs-lookup"><span data-stu-id="22c35-107">276</span></span>|  
|<span data-ttu-id="22c35-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="22c35-108">Event Source</span></span>|<span data-ttu-id="22c35-109">Runtime de base de données locale SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="22c35-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="22c35-110">Composant</span><span class="sxs-lookup"><span data-stu-id="22c35-110">Component</span></span>|<span data-ttu-id="22c35-111">API d'exécution de la base de données locale</span><span class="sxs-lookup"><span data-stu-id="22c35-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="22c35-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="22c35-112">Message Text</span></span>|<span data-ttu-id="22c35-113">La tampon transmis à la méthode d'API d'instance de base de données locale a une taille insuffisante.</span><span class="sxs-lookup"><span data-stu-id="22c35-113">The buffer passed to the Local Database instance API method has insufficient size.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="22c35-114">Explication</span><span class="sxs-lookup"><span data-stu-id="22c35-114">Explanation</span></span>  
 <span data-ttu-id="22c35-115">Le tampon d'entrée est trop court, et la troncation n'a pas été demandée.</span><span class="sxs-lookup"><span data-stu-id="22c35-115">The input buffer is too short, and truncation was not requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="22c35-116">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="22c35-116">User Action</span></span>  
 <span data-ttu-id="22c35-117">Fournissez un tampon de la taille spécifiée.</span><span class="sxs-lookup"><span data-stu-id="22c35-117">Provide a buffer of the specified size.</span></span>  
  
  
