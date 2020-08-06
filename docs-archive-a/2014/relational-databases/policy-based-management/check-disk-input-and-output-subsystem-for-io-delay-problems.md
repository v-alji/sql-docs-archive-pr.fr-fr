---
title: Rechercher des problèmes de délai d’E/S dans le sous-système d’E/S disque | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 23863340-d8e0-48d6-928b-462745885d37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0ae8dc0d1a93f8150ccbeab73ed8aa918d1f495
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699474"
---
# <a name="check-disk-input-and-output-subsystem-for-io-delay-problems"></a><span data-ttu-id="04cb9-102">Rechercher des problèmes de délai d’E/S dans le sous-système d’E/S disque</span><span class="sxs-lookup"><span data-stu-id="04cb9-102">Check Disk Input and Output Subsystem for IO Delay Problems</span></span>
  <span data-ttu-id="04cb9-103">Cette règle recherche le message d'erreur 833 dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="04cb9-103">This rule checks the event log for error message 833.</span></span> <span data-ttu-id="04cb9-104">Ce message indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a émis une demande de lecture ou d'écriture à partir du disque et que la demande a mis plus de 15 secondes à retourner un résultat.</span><span class="sxs-lookup"><span data-stu-id="04cb9-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="04cb9-105">Cette erreur est signalée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et indique un problème avec le sous-système d'E/S disque.</span><span class="sxs-lookup"><span data-stu-id="04cb9-105">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the disk I/O subsystem.</span></span> <span data-ttu-id="04cb9-106">Des délais de cette importance peuvent sévèrement nuire aux performances de votre environnement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04cb9-106">Delays this long can severely damage the performance of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="04cb9-107">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="04cb9-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="04cb9-108">Essayez de résoudre le problème en recherchant dans le journal des événements système d'éventuels messages d'erreur liés au matériel.</span><span class="sxs-lookup"><span data-stu-id="04cb9-108">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="04cb9-109">Examinez également les journaux spécifiques au matériel s'ils sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="04cb9-109">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="04cb9-110">Utilisez l'Analyseur de performances pour consulter les compteurs suivants :</span><span class="sxs-lookup"><span data-stu-id="04cb9-110">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="04cb9-111">Moy. disque s/transfert</span><span class="sxs-lookup"><span data-stu-id="04cb9-111">Average Disk Sec/Transfer</span></span>  
  
-   <span data-ttu-id="04cb9-112">Longueur moyenne de la file d'attente du disque</span><span class="sxs-lookup"><span data-stu-id="04cb9-112">Average Disk Queue Length</span></span>  
  
-   <span data-ttu-id="04cb9-113">Longueur actuelle de la file d'attente du disque</span><span class="sxs-lookup"><span data-stu-id="04cb9-113">Current Disk Queue Length</span></span>  
  
 <span data-ttu-id="04cb9-114">Par exemple, la Moy. disque s/transfert sur un ordinateur exécutant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est généralement inférieure à 15 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="04cb9-114">For example, the Average Disk Sec/Transfer time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="04cb9-115">Si la valeur Moy. disque s/transfert augmente, cela indique que le sous-système d'E/S disque ne parvient pas parfaitement à suivre la demande d'E/S.</span><span class="sxs-lookup"><span data-stu-id="04cb9-115">If the Average Disk Sec/Transfer value increases, this indicates that the disk I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="04cb9-116">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="04cb9-116">For More Information</span></span>  
 [<span data-ttu-id="04cb9-117">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="04cb9-117">MSSQLSERVER_833</span></span>](../errors-events/mssqlserver-833-database-engine-error.md)  
  
 [<span data-ttu-id="04cb9-118">Article 897284 de la Base de connaissances Microsoft</span><span class="sxs-lookup"><span data-stu-id="04cb9-118">Microsoft Knowledge Base article 897284</span></span>](https://go.microsoft.com/fwlink/?linkid=117743)  
  
 <span data-ttu-id="04cb9-119">[SQL Server I/O Basics, Chapter 2 (en anglais)](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="04cb9-119">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
