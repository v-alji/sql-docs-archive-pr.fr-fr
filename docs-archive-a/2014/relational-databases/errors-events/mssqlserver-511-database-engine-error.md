---
title: MSSQLSERVER_511 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 511 (Database Engine error)
ms.assetid: 0c85686a-53c1-4180-ba8c-2000e68a0d63
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5b69d2c043997e2947563de119bc4ee89fdf4e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698238"
---
# <a name="mssqlserver_511"></a><span data-ttu-id="4faf0-102">MSSQLSERVER_511</span><span class="sxs-lookup"><span data-stu-id="4faf0-102">MSSQLSERVER_511</span></span>
    
## <a name="details"></a><span data-ttu-id="4faf0-103">Détails</span><span class="sxs-lookup"><span data-stu-id="4faf0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4faf0-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="4faf0-104">Product Name</span></span>|<span data-ttu-id="4faf0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4faf0-105">SQL Server</span></span>|  
|<span data-ttu-id="4faf0-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="4faf0-106">Event ID</span></span>|<span data-ttu-id="4faf0-107">511</span><span class="sxs-lookup"><span data-stu-id="4faf0-107">511</span></span>|  
|<span data-ttu-id="4faf0-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="4faf0-108">Event Source</span></span>|<span data-ttu-id="4faf0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4faf0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4faf0-110">Composant</span><span class="sxs-lookup"><span data-stu-id="4faf0-110">Component</span></span>|<span data-ttu-id="4faf0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4faf0-111">SQLEngine</span></span>|  
|<span data-ttu-id="4faf0-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="4faf0-112">Symbolic Name</span></span>|<span data-ttu-id="4faf0-113">ROW_TOOBIG</span><span class="sxs-lookup"><span data-stu-id="4faf0-113">ROW_TOOBIG</span></span>|  
|<span data-ttu-id="4faf0-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="4faf0-114">Message Text</span></span>|<span data-ttu-id="4faf0-115">Impossible de créer une ligne de dimension %d supérieure au maximum autorisé %d.</span><span class="sxs-lookup"><span data-stu-id="4faf0-115">Cannot create a row of size %d which is greater than the allowable maximum of %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4faf0-116">Explication</span><span class="sxs-lookup"><span data-stu-id="4faf0-116">Explanation</span></span>  
 <span data-ttu-id="4faf0-117">L'opération que vous avez tentée a dépassé la taille maximale d'une ligne.</span><span class="sxs-lookup"><span data-stu-id="4faf0-117">The operation you have tried has exceeded the maximum size of a row.</span></span> <span data-ttu-id="4faf0-118">Habituellement, la taille maximale d'une ligne est 8 060 octets.</span><span class="sxs-lookup"><span data-stu-id="4faf0-118">Usually, the maximum size of a row is 8,060 bytes.</span></span> <span data-ttu-id="4faf0-119">Certains formats de stockage contiennent une surcharge susceptible de réduire la taille de ligne disponible pour les données.</span><span class="sxs-lookup"><span data-stu-id="4faf0-119">Some storage formats contain overhead that can reduce the row size that is available for data.</span></span> <span data-ttu-id="4faf0-120">Par exemple, lorsque vous utilisez des colonnes éparses, la taille maximale d'une ligne est 8 018 octets.</span><span class="sxs-lookup"><span data-stu-id="4faf0-120">For example, when you use sparse columns, the maximum size of a row is 8,018 bytes.</span></span> <span data-ttu-id="4faf0-121">Certaines opérations qui ajoutent ou suppriment des lignes et certaines opérations qui modifient le type de données d'une colonne exigent que la ligne soit réécrite dans la page de données et que la ligne d'origine soit ensuite supprimée.</span><span class="sxs-lookup"><span data-stu-id="4faf0-121">Some operations that add or remove rows and some operations that change the data type of a column require the row to be rewritten on the data page, and then the original row is removed.</span></span> <span data-ttu-id="4faf0-122">Dans ces opérations, la limite effective de la taille de la ligne correspond à la moitié de la limite maximale.</span><span class="sxs-lookup"><span data-stu-id="4faf0-122">In these operations, the effective limit to the size of the row is half the maximum limit.</span></span> <span data-ttu-id="4faf0-123">Cela est dû au fait que la ligne d'origine et la ligne modifiée doivent toutes les deux être incluses dans la page de données pour une courte période.</span><span class="sxs-lookup"><span data-stu-id="4faf0-123">This is because the original row and the modified row must both be contained on the data page for a short period.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="4faf0-124">Chaque colonne **varchar (max)** ou **nvarchar (max)** non null requiert 24 octets d’allocation fixe supplémentaire qui est comptabilisée par rapport à la limite de 8 060 octets par ligne pendant une opération de tri.</span><span class="sxs-lookup"><span data-stu-id="4faf0-124">Each non-null  **varchar(max)** or **nvarchar(max)** column requires 24 bytes of additional fixed allocation which counts against the 8,060 byte row limit during a sort operation.</span></span> <span data-ttu-id="4faf0-125">Cela peut créer une limite implicite du nombre de colonnes **varchar (max)** ou **nvarchar (max)** non null pouvant être créées dans une table.</span><span class="sxs-lookup"><span data-stu-id="4faf0-125">This can create an implicit limit to the number of non-null **varchar(max)** or **nvarchar(max)** columns that can be created in a table.</span></span> <span data-ttu-id="4faf0-126">Aucune erreur spéciale n'est fournie quand la table est créée (mis à part l’avertissement habituel indiquant que la taille maximale de ligne dépasse la taille maximale autorisée de 8 060 octets) ou quand les données sont insérées.</span><span class="sxs-lookup"><span data-stu-id="4faf0-126">No special error is provided when the table is created (beyond the usual warning that the maximum row size exceeds the allowed maximum of 8060 bytes) or at the time of data insertion.</span></span> <span data-ttu-id="4faf0-127">Cette grande taille de ligne peut provoquer des erreurs (comme l’erreur 512) au cours des opérations normales, telles que la mise à jour de la clé d’index cluster ou le tri de l’intégralité des colonnes, que les utilisateurs ne peuvent pas anticiper tant qu’elles n’ont pas été effectuées.</span><span class="sxs-lookup"><span data-stu-id="4faf0-127">This large row size can cause errors (such as error 512) during some normal operations, such as a clustered index key update, or sorts of the full column set, which users cannot anticipate until performing an operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4faf0-128">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4faf0-128">User Action</span></span>  
 <span data-ttu-id="4faf0-129">Si cela est possible, réduisez la taille de la ligne.</span><span class="sxs-lookup"><span data-stu-id="4faf0-129">If it is possible, reduce the size of the row.</span></span>  
  
 <span data-ttu-id="4faf0-130">Si vous pensez que le problème provient d'une mise à jour sur place de la ligne, vous devez modifier la table en plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="4faf0-130">If you think the problem is caused by an in-place update of the row, you must change the table in multiple steps.</span></span> <span data-ttu-id="4faf0-131">Créez une nouvelle table et transférez les données dans la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="4faf0-131">Create a new table, and transfer the data into the new table.</span></span> <span data-ttu-id="4faf0-132">Ensuite, supprimez la table d'origine et renommez la nouvelle table, ou tronquez la table d'origine, modifiez les lignes dans la table d'origine, puis replacez les données dans cette table.</span><span class="sxs-lookup"><span data-stu-id="4faf0-132">Then, either delete the original table and rename the new table, or truncate the original table, modify the rows in the original table, and then move the data back into it.</span></span>  
  
  
