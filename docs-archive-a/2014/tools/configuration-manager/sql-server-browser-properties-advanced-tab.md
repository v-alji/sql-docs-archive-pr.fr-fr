---
title: Propriétés de SQL Server Browser (onglet Avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ba79137a-cb72-4bf3-a650-e11d02cfce10
author: stevestein
ms.author: sstein
ms.openlocfilehash: 480cd93c3feca44dd455a1a9ce2fd12994ca6100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613244"
---
# <a name="sql-server-browser-properties-advanced-tab"></a><span data-ttu-id="1b41f-102">Propriétés de SQL Server Browser (onglet Avancé)</span><span class="sxs-lookup"><span data-stu-id="1b41f-102">SQL Server Browser Properties (Advanced Tab)</span></span>
  <span data-ttu-id="1b41f-103">Le programme [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser s'exécute sur le serveur en tant que service.</span><span class="sxs-lookup"><span data-stu-id="1b41f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1b41f-104">Browser est à l’écoute des demandes entrantes pour les ressources [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et fournit des informations sur les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installées sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1b41f-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1b41f-105">Options</span><span class="sxs-lookup"><span data-stu-id="1b41f-105">Options</span></span>  
 <span data-ttu-id="1b41f-106">**Cluster**</span><span class="sxs-lookup"><span data-stu-id="1b41f-106">**Clustered**</span></span>  
 <span data-ttu-id="1b41f-107">Indique si ce service est installé en tant que ressource d'un serveur cluster.</span><span class="sxs-lookup"><span data-stu-id="1b41f-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="1b41f-108">**Commentaires client**</span><span class="sxs-lookup"><span data-stu-id="1b41f-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="1b41f-109">Indique si le contrôle SQM (Service Quality Monitoring) a été activé sur ce service.</span><span class="sxs-lookup"><span data-stu-id="1b41f-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="1b41f-110">Pour plus d'informations sur Commentaires client, recherchez dans la documentation en ligne la rubrique « Paramètres des rapports d'erreurs et d'utilisation ».</span><span class="sxs-lookup"><span data-stu-id="1b41f-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="1b41f-111">**Répertoire de vidage**</span><span class="sxs-lookup"><span data-stu-id="1b41f-111">**Dump Directory**</span></span>  
 <span data-ttu-id="1b41f-112">Emplacement où sont placés les vidages de mémoire en cas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="1b41f-112">The location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="1b41f-113">**Rapport d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="1b41f-113">**Error Reporting**</span></span>  
 <span data-ttu-id="1b41f-114">Quand cette option a pour valeur **Oui**, le programme Dr Watson transfère les informations à [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou au serveur d'erreur en cas de problème sérieux.</span><span class="sxs-lookup"><span data-stu-id="1b41f-114">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="1b41f-115">Pour plus d'informations sur les rapports d'erreurs, recherchez dans la documentation en ligne la rubrique « Paramètres des rapports d'erreurs et d'utilisation ».</span><span class="sxs-lookup"><span data-stu-id="1b41f-115">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="1b41f-116">**ID de l'instance**</span><span class="sxs-lookup"><span data-stu-id="1b41f-116">**Instance ID**</span></span>  
 <span data-ttu-id="1b41f-117">Indique l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui a utilisé cette instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="1b41f-117">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance.</span></span> <span data-ttu-id="1b41f-118">L’instance par défaut est **MSSQL10_50.MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="1b41f-118">The default instance is **MSSQL10_50.MSSQLSERVER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b41f-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b41f-119">See Also</span></span>  
 [<span data-ttu-id="1b41f-120">Service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="1b41f-120">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
