---
title: Configurer les journaux d’erreurs de SQL Server Agent (page Général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.errorlog.configure.f1
ms.assetid: e08de622-6f87-470c-aee0-b2d6cb6cca88
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd4c083ea7e7d220d5da20594079b7679c0bb724
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611498"
---
# <a name="configure-sql-server-agent-error-logs-general-page"></a><span data-ttu-id="a59b5-102">Configurer les journaux d'erreurs de l'Agent SQL Server (page Général)</span><span class="sxs-lookup"><span data-stu-id="a59b5-102">Configure SQL Server Agent Error Logs (General Page)</span></span>
  <span data-ttu-id="a59b5-103">Utilisez cet écran pour afficher et mettre à jour les paramètres du journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a59b5-103">Use this screen to view and update settings for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logging.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a59b5-104">Options</span><span class="sxs-lookup"><span data-stu-id="a59b5-104">Options</span></span>  
 <span data-ttu-id="a59b5-105">**Fichier journal des erreurs**</span><span class="sxs-lookup"><span data-stu-id="a59b5-105">**Error log file**</span></span>  
 <span data-ttu-id="a59b5-106">Spécifie le nom du fichier dans lequel l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consigne les erreurs.</span><span class="sxs-lookup"><span data-stu-id="a59b5-106">Specifies the file to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes error logs.</span></span>  
  
 <span data-ttu-id="a59b5-107">**...**</span><span class="sxs-lookup"><span data-stu-id="a59b5-107">**...**</span></span>  
 <span data-ttu-id="a59b5-108">Permet de parcourir l'arborescence à la recherche du fichier journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="a59b5-108">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="a59b5-109">**Écrire dans le fichier journal des erreurs OEM**</span><span class="sxs-lookup"><span data-stu-id="a59b5-109">**Write OEM error log**</span></span>  
 <span data-ttu-id="a59b5-110">Écrit le fichier journal des erreurs comme un fichier non-Unicode.</span><span class="sxs-lookup"><span data-stu-id="a59b5-110">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="a59b5-111">Cela réduit l'espace disque utilisé par le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a59b5-111">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="a59b5-112">Toutefois, si vous activez cette option, sachez que les messages incluant des données Unicode peuvent être plus difficiles à lire.</span><span class="sxs-lookup"><span data-stu-id="a59b5-112">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="a59b5-113">**Erreurs**</span><span class="sxs-lookup"><span data-stu-id="a59b5-113">**Errors**</span></span>  
 <span data-ttu-id="a59b5-114">Écrit uniquement les erreurs et les messages d'information dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a59b5-114">Writes only errors and informational messages to the log file.</span></span>  
  
 <span data-ttu-id="a59b5-115">**Avertissements**</span><span class="sxs-lookup"><span data-stu-id="a59b5-115">**Warnings**</span></span>  
 <span data-ttu-id="a59b5-116">Écrit uniquement les avertissements et les messages d'information dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a59b5-116">Writes only warnings and informational messages to the log file.</span></span>  
  
 <span data-ttu-id="a59b5-117">**Informations**</span><span class="sxs-lookup"><span data-stu-id="a59b5-117">**Information**</span></span>  
 <span data-ttu-id="a59b5-118">Écrit uniquement les messages d'information dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a59b5-118">Writes only informational messages to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a59b5-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a59b5-119">See Also</span></span>  
 [<span data-ttu-id="a59b5-120">Journal des erreurs de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="a59b5-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
