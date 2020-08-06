---
title: MSSQLSERVER_15661 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15661 (Database Engine error)
ms.assetid: 88b01bfb-74ce-4aa0-aec0-7885261c7ef3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 966e23e8d970c36eba81253228cc18ed4af3ff77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600054"
---
# <a name="mssqlserver_15661"></a><span data-ttu-id="71ab5-102">MSSQLSERVER_15661</span><span class="sxs-lookup"><span data-stu-id="71ab5-102">MSSQLSERVER_15661</span></span>
    
## <a name="details"></a><span data-ttu-id="71ab5-103">Détails</span><span class="sxs-lookup"><span data-stu-id="71ab5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="71ab5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="71ab5-104">Product Name</span></span>|<span data-ttu-id="71ab5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="71ab5-105">SQL Server</span></span>|  
|<span data-ttu-id="71ab5-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="71ab5-106">Event ID</span></span>|<span data-ttu-id="71ab5-107">15661</span><span class="sxs-lookup"><span data-stu-id="71ab5-107">15661</span></span>|  
|<span data-ttu-id="71ab5-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="71ab5-108">Event Source</span></span>|<span data-ttu-id="71ab5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="71ab5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="71ab5-110">Composant</span><span class="sxs-lookup"><span data-stu-id="71ab5-110">Component</span></span>|<span data-ttu-id="71ab5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="71ab5-111">SQLEngine</span></span>|  
|<span data-ttu-id="71ab5-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="71ab5-112">Symbolic Name</span></span>|<span data-ttu-id="71ab5-113">SQLErrorNum15661</span><span class="sxs-lookup"><span data-stu-id="71ab5-113">SQLErrorNum15661</span></span>|  
|<span data-ttu-id="71ab5-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="71ab5-114">Message Text</span></span>|<span data-ttu-id="71ab5-115">La procédure stockée sp_estimate_data_compression_savings ne peut pas être utilisée pour les tables temporaires.</span><span class="sxs-lookup"><span data-stu-id="71ab5-115">The sp_estimate_data_compression_savings stored procedure cannot be used for temporary tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="71ab5-116">Explication</span><span class="sxs-lookup"><span data-stu-id="71ab5-116">Explanation</span></span>  
 <span data-ttu-id="71ab5-117">Une table temporaire a été utilisée comme argument de la procédure stockée sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="71ab5-117">A temporary table was used as an argument for the sp_estimate_data_compression_savings stored procedure.</span></span> <span data-ttu-id="71ab5-118">Bien que la compression de tables temporaires soit prise en charge, vous ne pouvez pas utiliser sp_estimate_data_compression_savings pour estimer les économies de compression.</span><span class="sxs-lookup"><span data-stu-id="71ab5-118">Although the compression of temporary tables is supported, you cannot use sp_estimate_data_compression_savings to estimate the compression savings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="71ab5-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="71ab5-119">User Action</span></span>  
 <span data-ttu-id="71ab5-120">Supprimez la table temporaire comme argument de sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="71ab5-120">Remove the temporary table as an argument for sp_estimate_data_compression_savings.</span></span>  
  
  
