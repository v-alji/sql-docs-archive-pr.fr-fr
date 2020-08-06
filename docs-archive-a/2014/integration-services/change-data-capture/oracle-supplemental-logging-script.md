---
title: Script de journalisation supplémentaire Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e6ee618-b89b-46c7-92ad-4fc5ef7b777a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0aa55e71c17574eba9e25e098a3881b0eb4c9e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695940"
---
# <a name="oracle-supplemental-logging-script"></a><span data-ttu-id="0b10a-102">Script de journalisation supplémentaire Oracle</span><span class="sxs-lookup"><span data-stu-id="0b10a-102">Oracle Supplemental Logging Script</span></span>
  <span data-ttu-id="0b10a-103">Cette boîte de dialogue affiche le script Oracle de journalisation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0b10a-103">This dialog box shows the script the Oracle supplemental logging script.</span></span>  
  
 <span data-ttu-id="0b10a-104">Lorsque vous préparez une instance de capture de données modifiées pour l'utilisation, le concepteur CDC crée un script Oracle SQL qui configure une journalisation supplémentaire pour les tables à capturer.</span><span class="sxs-lookup"><span data-stu-id="0b10a-104">When you prepare a CDC Instance for use, the CDC Designer creates an Oracle SQL script that sets up supplemental logging for the tables to be captured.</span></span> <span data-ttu-id="0b10a-105">Le script de journalisation supplémentaire indique à Oracle que lorsqu'une table spécifique est mise à jour, les enregistrements de modification qu'elle écrit dans le journal des transactions doivent contenir les données de toutes les colonnes d'intérêt, et non pas seulement des colonnes qui ont été modifiées.</span><span class="sxs-lookup"><span data-stu-id="0b10a-105">The supplemental logging script tells Oracle that when a specific table is updated, the change records it writes to the transaction log should contain the data of all columns of interest, not just the columns that changed.</span></span>  
  
 <span data-ttu-id="0b10a-106">Selon les stratégies de l'administrateur de base de données Oracle de votre organisation, l'exécution du script de journalisation supplémentaire peut nécessiter un examen et une approbation par un administrateur de base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="0b10a-106">Depending on the Oracle DBA policies in your organization, running the supplemental logging script may require a review and approval by an Oracle DBA.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0b10a-107">Options</span><span class="sxs-lookup"><span data-stu-id="0b10a-107">Options</span></span>  
 <span data-ttu-id="0b10a-108">Voici les options disponibles pour l'exécution du script.</span><span class="sxs-lookup"><span data-stu-id="0b10a-108">The following are the available options for how to execute the script.</span></span>  
  
 <span data-ttu-id="0b10a-109">**Exécuter un script**</span><span class="sxs-lookup"><span data-stu-id="0b10a-109">**Run Script**</span></span>  
 <span data-ttu-id="0b10a-110">Exécute le script de journalisation supplémentaire sur les tables définies pour l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="0b10a-110">Runs the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="0b10a-111">Pour exécuter ce script, l'utilisateur Oracle doit disposer de l'autorisation ALTER TABLE pour que toutes les tables soient capturées et de l'autorisation SELECT sur la vue DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="0b10a-111">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span> <span data-ttu-id="0b10a-112">En outre, l'utilisateur Oracle doit disposer des informations d'identification pour utiliser une base de données Oracle avec les autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="0b10a-112">In addition, the Oracle user must have the credentials for an Oracle database use with the required permissions.</span></span> <span data-ttu-id="0b10a-113">Vous pouvez laisser le programme vous inviter à entrer les informations d'identification Oracle, puis exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="0b10a-113">You can let the program prompt you for the Oracle credentials and then have it run the script.</span></span>  
  
 <span data-ttu-id="0b10a-114">**Enregistrer sous**</span><span class="sxs-lookup"><span data-stu-id="0b10a-114">**Save As**</span></span>  
 <span data-ttu-id="0b10a-115">Enregistre le script dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="0b10a-115">Saves the script to a text file.</span></span> <span data-ttu-id="0b10a-116">Cette option est utilisée si un administrateur de base de données Oracle (DBA) doit examiner et exécuter le script de journalisation supplémentaire, le programme vous permet d'enregistrer le script dans un fichier texte que vous pouvez ultérieurement envoyer à l'administrateur de base de données Oracle par courrier électronique ou par d'autres moyens en vue de son exécution ultérieure (à l'aide de l'utilitaire SQL\*PLUS Oracle ou d'un autre outil pour exécuter des scripts sur une base de données Oracle).</span><span class="sxs-lookup"><span data-stu-id="0b10a-116">This is used if an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script, the program lets you save the script to a text file that you can later send to the Oracle DBA by email or by other means to be execute later (by using the SQL\*Plus Oracle utility or other tool for running scripts on an Oracle database).</span></span>  
  
 <span data-ttu-id="0b10a-117">**Copy**</span><span class="sxs-lookup"><span data-stu-id="0b10a-117">**Copy**</span></span>  
 <span data-ttu-id="0b10a-118">Copie le script dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="0b10a-118">Copies the script to the clipboard.</span></span> <span data-ttu-id="0b10a-119">Lorsque vous serez prêt, vous pourrez coller le script dans n'importe quel emplacement si un administrateur de base de données Oracle (DBA) doit examiner et exécuter le script de journalisation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0b10a-119">When ready you can paste the script in any location you need in case an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b10a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b10a-120">See Also</span></span>  
 <span data-ttu-id="0b10a-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="0b10a-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="0b10a-122">Gérer une instance CDC</span><span class="sxs-lookup"><span data-stu-id="0b10a-122">Manage a CDC Instance</span></span>](manage-a-cdc-instance.md)  
  
  
