---
title: Rechercher les problèmes de nouvelle tentative de lecture dans le sous-système de sortie d’entrée de disque | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19809b1554e435600eb4eeae424bed17dc27bdbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695587"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a><span data-ttu-id="d8de5-102">Rechercher des problèmes de nouvelle tentative de lecture dans le sous-système d’E/S disque</span><span class="sxs-lookup"><span data-stu-id="d8de5-102">Check Disk Input Output Subsystem for Read Retry Problems</span></span>
  <span data-ttu-id="d8de5-103">Cette règle recherche le message d'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 825 dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="d8de5-103">This rule checks the event log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message 825.</span></span> <span data-ttu-id="d8de5-104">Ce message indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'a pas pu lire les données du disque à la première tentative.</span><span class="sxs-lookup"><span data-stu-id="d8de5-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to read data from the disk on the first try.</span></span> <span data-ttu-id="d8de5-105">Ce message signale un problème majeur avec le sous-système d'E/S.</span><span class="sxs-lookup"><span data-stu-id="d8de5-105">This message indicates a major problem with the disk I/O subsystem.</span></span> <span data-ttu-id="d8de5-106">Il n’indique pas un problème avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8de5-106">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem.</span></span> <span data-ttu-id="d8de5-107">Toutefois, le problème de disque peut entraîner la perte de données ou l'altération des bases de données s'il n'est pas résolu.</span><span class="sxs-lookup"><span data-stu-id="d8de5-107">However, the disk problem could cause data loss or database corruption if it is not resolved.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="d8de5-108">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="d8de5-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="d8de5-109">Les actions suivantes peuvent vous aider à identifier et à résoudre le problème matériel sous-jacent :</span><span class="sxs-lookup"><span data-stu-id="d8de5-109">The following actions might help you discover and resolve the underlying hardware problem:</span></span>  
  
-   <span data-ttu-id="d8de5-110">Consultez le journal des erreurs et le texte spécifique de ce message pour trouver des indications expliquant pourquoi le problème s'est produit.</span><span class="sxs-lookup"><span data-stu-id="d8de5-110">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="d8de5-111">Vérifiez le système de disques.</span><span class="sxs-lookup"><span data-stu-id="d8de5-111">Check the disk system.</span></span> <span data-ttu-id="d8de5-112">Le problème peut être lié aux disques, aux contrôleurs de disques, aux cartes de disques ou aux pilotes de disques.</span><span class="sxs-lookup"><span data-stu-id="d8de5-112">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="d8de5-113">Contactez le fabricant de vos disques pour vous procurer les utilitaires les plus récents permettant de vérifier l'état de votre système de disques.</span><span class="sxs-lookup"><span data-stu-id="d8de5-113">Contact the disk manufacturer for the latest utilities for checking the status of the disk system.</span></span>  
  
-   <span data-ttu-id="d8de5-114">Contactez le fabricant de vos disques pour obtenir les dernières mises à jour des pilotes.</span><span class="sxs-lookup"><span data-stu-id="d8de5-114">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="d8de5-115">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="d8de5-115">For More Information</span></span>  
 [<span data-ttu-id="d8de5-116">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="d8de5-116">MSSQLSERVER_825</span></span>](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 <span data-ttu-id="d8de5-117">[SQL Server I/O Basics, Chapter 2 (en anglais)](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d8de5-117">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
