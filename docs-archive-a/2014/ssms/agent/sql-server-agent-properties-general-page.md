---
title: Propriétés de SQL Server Agent (page Général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.general.f1
ms.assetid: b51601e9-5454-43c6-bb5e-24eb2ff043c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: a67d5431be4025c18b11d6791b016fa83e957810
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613262"
---
# <a name="sql-server-agent-properties-general-page"></a><span data-ttu-id="a150e-102">Propriétés de SQL Server Agent (page Général)</span><span class="sxs-lookup"><span data-stu-id="a150e-102">SQL Server Agent Properties (General Page)</span></span>
  <span data-ttu-id="a150e-103">Utilisez cette page pour afficher et modifier les propriétés générales du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service agent.</span><span class="sxs-lookup"><span data-stu-id="a150e-103">Use this page to view and modify the general properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a150e-104">Options</span><span class="sxs-lookup"><span data-stu-id="a150e-104">Options</span></span>  
 <span data-ttu-id="a150e-105">**État du service**</span><span class="sxs-lookup"><span data-stu-id="a150e-105">**Service state**</span></span>  
 <span data-ttu-id="a150e-106">Affiche l'état actuel du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a150e-106">Displays the current state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
 <span data-ttu-id="a150e-107">**Redémarrage automatique de SQL Server après un arrêt inattendu**</span><span class="sxs-lookup"><span data-stu-id="a150e-107">**Auto restart SQL Server if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a150e-108">Agent redémarre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cas d’arrêt inattendu de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a150e-108">Agent restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stops unexpectedly.</span></span>  
  
 <span data-ttu-id="a150e-109">**Redémarrage automatique de l'Agent SQL Server après un arrêt inattendu**</span><span class="sxs-lookup"><span data-stu-id="a150e-109">**Auto restart SQL Server Agent if it stops unexpectedly**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a150e-110">redémarre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent en cas d’arrêt inattendu de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a150e-110">restarts [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stops unexpectedly.</span></span>  
  
 <span data-ttu-id="a150e-111">**Extension**</span><span class="sxs-lookup"><span data-stu-id="a150e-111">**Filename**</span></span>  
 <span data-ttu-id="a150e-112">Spécifiez le nom de fichier du journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="a150e-112">Specify the file name for the error log.</span></span>  
  
 <span data-ttu-id="a150e-113">**...**</span><span class="sxs-lookup"><span data-stu-id="a150e-113">**...**</span></span>  
 <span data-ttu-id="a150e-114">Permet de parcourir l'arborescence à la recherche du fichier journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="a150e-114">Browse to the error log file.</span></span>  
  
 <span data-ttu-id="a150e-115">**Inclure les messages de trace d'exécution**</span><span class="sxs-lookup"><span data-stu-id="a150e-115">**Include execution trace messages**</span></span>  
 <span data-ttu-id="a150e-116">Inclut des messages de trace d'exécution dans le journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="a150e-116">Includes execution trace messages in the error log.</span></span> <span data-ttu-id="a150e-117">Les messages de trace fournissent des informations détaillées sur le fonctionnement de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a150e-117">Trace messages provide detailed information on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operation.</span></span> <span data-ttu-id="a150e-118">Le fichier journal nécessite donc davantage d'espace disque lorsque cette option est activée.</span><span class="sxs-lookup"><span data-stu-id="a150e-118">Therefore, the log file requires more disk space when this option is selected.</span></span> <span data-ttu-id="a150e-119">Vous ne devez activer cette option que pour résoudre un problème susceptible d'impliquer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="a150e-119">This option should only be selected while troubleshooting a problem that may involve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="a150e-120">**Enregistrer le fichier OEM**</span><span class="sxs-lookup"><span data-stu-id="a150e-120">**Write OEM file**</span></span>  
 <span data-ttu-id="a150e-121">Écrit le fichier journal des erreurs comme un fichier non-Unicode.</span><span class="sxs-lookup"><span data-stu-id="a150e-121">Writes the error log file as a non-Unicode file.</span></span> <span data-ttu-id="a150e-122">Cela réduit l'espace disque utilisé par le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a150e-122">This reduces the amount of disk space consumed by the log file.</span></span> <span data-ttu-id="a150e-123">Toutefois, si vous activez cette option, sachez que les messages incluant des données Unicode peuvent être plus difficiles à lire.</span><span class="sxs-lookup"><span data-stu-id="a150e-123">However, messages that include Unicode data may be more difficult to read when this option is enabled.</span></span>  
  
 <span data-ttu-id="a150e-124">**Destinataire d'envoi réseau**</span><span class="sxs-lookup"><span data-stu-id="a150e-124">**Net send recipient**</span></span>  
 <span data-ttu-id="a150e-125">Tapez le nom d'un opérateur destiné à recevoir la notification envoyée par réseau des messages que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent consigne dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="a150e-125">Type the name of an operator to receive net send notification of messages that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent writes to the log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a150e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a150e-126">See Also</span></span>  
 <span data-ttu-id="a150e-127">[Operator](operators.md) </span><span class="sxs-lookup"><span data-stu-id="a150e-127">[Operators](operators.md) </span></span>  
 [<span data-ttu-id="a150e-128">Journal des erreurs de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="a150e-128">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
