---
title: Éditeur du gestionnaire de connexions de l’édition SQL Server Compact (page tout) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlmobileconnection.all.f1
helpviewer_keywords:
- SQL Server Compact Connection Manager Editor
ms.assetid: f9fbff4b-c502-44b3-8e7b-398d66e82206
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f881d63de5435426475c3aed4b666870d706b40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604040"
---
# <a name="sql-server-compact-edition-connection-manager-editor-all-page"></a><span data-ttu-id="a5ba6-102">Éditeur du gestionnaire de connexions SQL Server Compact Edition (page Tout)</span><span class="sxs-lookup"><span data-stu-id="a5ba6-102">SQL Server Compact Edition Connection Manager Editor (All Page)</span></span>
  <span data-ttu-id="a5ba6-103">La boîte de dialogue **Éditeur du gestionnaire de connexions SQL Server Compact Edition** permet de spécifier les propriétés permettant de se connecter à une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-103">Use the **SQL Server Compact Edition Connection Manager** dialog box to specify properties for connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="a5ba6-104">Pour en savoir plus sur le gestionnaire de connexions [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition, consultez [Éditeur du gestionnaire de connexions SQL Server Compact Edition](connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a5ba6-104">To learn more about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact Edition connection manager, see [SQL Server Compact Edition Connection Manager](connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5ba6-105">Options</span><span class="sxs-lookup"><span data-stu-id="a5ba6-105">Options</span></span>  
 <span data-ttu-id="a5ba6-106">**AutoShrink Threshold**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-106">**AutoShrink Threshold**</span></span>  
 <span data-ttu-id="a5ba6-107">Spécifiez le pourcentage d’espace libre autorisé dans la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact avant que le processus de réduction automatique soit lancé.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-107">Specify the amount of free space, as a percentage, that is allowed in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database before the autoshrink process runs.</span></span>  
  
 <span data-ttu-id="a5ba6-108">**Escalade de verrous par défaut**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-108">**Default Lock Escalation**</span></span>  
 <span data-ttu-id="a5ba6-109">Spécifiez le nombre de verrous de base de données acquis par la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact avant qu’elle tente de promouvoir les verrous.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-109">Specify the number of database locks that the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database acquires before it tries to escalate locks.</span></span>  
  
 <span data-ttu-id="a5ba6-110">**Default Lock Timeout**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-110">**Default Lock Timeout**</span></span>  
 <span data-ttu-id="a5ba6-111">Spécifiez l'intervalle par défaut, en millisecondes, d'attente d'un verrou par une instruction.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-111">Specify the default interval, in milliseconds, that a transaction will wait for a lock.</span></span>  
  
 <span data-ttu-id="a5ba6-112">**Flush Interval**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-112">**Flush Interval**</span></span>  
 <span data-ttu-id="a5ba6-113">Spécifiez l'intervalle, en secondes, s'écoulant entre les vidages de données de transactions validées sur le disque.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-113">Specify the interval, in seconds, between committed transactions to flush data to disk.</span></span>  
  
 <span data-ttu-id="a5ba6-114">**Identificateur de paramètres régionaux**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-114">**Locale Identifier**</span></span>  
 <span data-ttu-id="a5ba6-115">Spécifiez l’identificateur de paramètres régionaux (LCID) de la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-115">Specify the Locale ID (LCID) of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="a5ba6-116">**Max Buffer Size**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-116">**Max Buffer Size**</span></span>  
 <span data-ttu-id="a5ba6-117">Spécifiez la quantité maximale de mémoire (en Ko) utilisée par [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact avant d’effectuer un vidage des données sur le disque.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-117">Specify the maximum amount of memory, in kilobytes, that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact uses before flushing data to disk.</span></span>  
  
 <span data-ttu-id="a5ba6-118">**Taille maximale de la base de données**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-118">**Max Database Size**</span></span>  
 <span data-ttu-id="a5ba6-119">Spécifiez la taille maximale (en Mo) de la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-119">Specify the maximum size, in megabytes, of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="a5ba6-120">**Mode**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-120">**Mode**</span></span>  
 <span data-ttu-id="a5ba6-121">Spécifiez le mode de fichier dans lequel ouvrir la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-121">Specify the file mode in which to open the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="a5ba6-122">La valeur par défaut de cette propriété est **Read Write**.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-122">The default value for this property is **Read Write**.</span></span>  
  
 <span data-ttu-id="a5ba6-123">L'option Mode comporte quatre valeurs, qui sont décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-123">The Mode option has four values, as described in the following table.</span></span>  
  
|<span data-ttu-id="a5ba6-124">Valeur</span><span class="sxs-lookup"><span data-stu-id="a5ba6-124">Value</span></span>|<span data-ttu-id="a5ba6-125">Description</span><span class="sxs-lookup"><span data-stu-id="a5ba6-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5ba6-126">**Lecture seule**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-126">**Read Only**</span></span>|<span data-ttu-id="a5ba6-127">Offre un accès en lecture seule à la base de données.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-127">Specifies read-only access to the database.</span></span>|  
|<span data-ttu-id="a5ba6-128">**Lecture/écriture**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-128">**Read Write**</span></span>|<span data-ttu-id="a5ba6-129">Autorise l'accès en lecture et écriture à la base de données.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-129">Specifies read/write permission to the database.</span></span>|  
|<span data-ttu-id="a5ba6-130">**Exclusive**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-130">**Exclusive**</span></span>|<span data-ttu-id="a5ba6-131">Offre un accès exclusif à la base de données.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-131">Specifies exclusive access to the database.</span></span>|  
|<span data-ttu-id="a5ba6-132">**Shared Read**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-132">**Shared Read**</span></span>|<span data-ttu-id="a5ba6-133">Indique que plusieurs utilisateurs peuvent lire la base de données simultanément.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-133">Specifies that other users can read from the database at the same time.</span></span>|  
  
 <span data-ttu-id="a5ba6-134">**Persist Security Info**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-134">**Persist Security Info**</span></span>  
 <span data-ttu-id="a5ba6-135">Indique si des informations de sécurité sont retournées dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-135">Specify whether security information is returned as part of the connection string.</span></span> <span data-ttu-id="a5ba6-136">La valeur par défaut de cette option est **false**.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-136">The default value for this option is **False**.</span></span>  
  
 <span data-ttu-id="a5ba6-137">**Temp File Directory**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-137">**Temp File Directory**</span></span>  
 <span data-ttu-id="a5ba6-138">Spécifiez l’emplacement du fichier de base de données temporaire de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-138">Specify the location of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact temporary database file.</span></span>  
  
 <span data-ttu-id="a5ba6-139">**Source de données**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-139">**Data Source**</span></span>  
 <span data-ttu-id="a5ba6-140">Spécifiez le nom de la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-140">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
 <span data-ttu-id="a5ba6-141">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="a5ba6-141">**Password**</span></span>  
 <span data-ttu-id="a5ba6-142">Entrez le mot de passe pour la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="a5ba6-142">Enter the password for the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ba6-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5ba6-143">See Also</span></span>  
 <span data-ttu-id="a5ba6-144">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a5ba6-144">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="a5ba6-145">Éditeur du gestionnaire de connexions SQL Server Compact Edition &#40;page Connexion&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ba6-145">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../../2014/integration-services/sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
  
