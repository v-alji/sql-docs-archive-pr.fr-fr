---
title: Script de déploiement d’instance CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fa82822-ac99-48ef-a18d-f4f3a77105b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6deea884168c2329e312eeaa2be16c28a955cca3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708559"
---
# <a name="cdc-instance-deployment-script"></a><span data-ttu-id="14ce0-102">Script de déploiement d'instance CDC</span><span class="sxs-lookup"><span data-stu-id="14ce0-102">CDC Instance Deployment Script</span></span>
  <span data-ttu-id="14ce0-103">Boîte de dialogue de script de déploiement d'instance de capture de données modifiées qui affiche le script de déploiement d'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="14ce0-103">The CDC Instance Deployment Script dialog box that displays the CDC instance deployment script.</span></span> <span data-ttu-id="14ce0-104">Ce script peut être utilisé pour recréer la base de données CDC avec tous ses artefacts sur une autre instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14ce0-104">This script can be used to re-create the CDC database with all of its artifacts on a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="14ce0-105">À la fin du script de déploiement, vous devez vous assurer de ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="14ce0-105">At the completion of the deployment script, you should make sure of the following:</span></span>  
  
-   <span data-ttu-id="14ce0-106">Le script de déploiement suppose que l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible a été préparée pour la capture de données modifiées Oracle, à l'aide de la console de configuration du service de capture de données modifiées Oracle ou à l'aide du **script de préparation** créé par le programme.</span><span class="sxs-lookup"><span data-stu-id="14ce0-106">The deployment script assumes that the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance was prepared for Oracle CDC, by using the Oracle CDC Service Configuration Console or by using **prepare script** that program creates.</span></span>  
  
-   <span data-ttu-id="14ce0-107">La partie du script utilisée pour activer la base de données pour la capture de données modifiées doit être exécutée par un `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="14ce0-107">The part of the script that is used to enable the database for CDC needs to be run by a `sysadmin`.</span></span>  
  
-   <span data-ttu-id="14ce0-108">Le script ne conserve pas le mot de passe d'exploration de données de journaux Oracle.</span><span class="sxs-lookup"><span data-stu-id="14ce0-108">The script does not preserve the Oracle log-mining password.</span></span> <span data-ttu-id="14ce0-109">Il doit être défini manuellement une fois le script exécuté et le service de capture de données modifiées Oracle démarré.</span><span class="sxs-lookup"><span data-stu-id="14ce0-109">This needs to be set manually after the script is run and the Oracle CDC Service is started.</span></span>  
  
 <span data-ttu-id="14ce0-110">Sélectionnez les options suivantes dans la boîte de dialogue **Script de déploiement d'instance CDC** .</span><span class="sxs-lookup"><span data-stu-id="14ce0-110">Select the following options in the **CDC Instance Deployment Script** dialog box.</span></span>  
  
 <span data-ttu-id="14ce0-111">**Enregistrer sous**</span><span class="sxs-lookup"><span data-stu-id="14ce0-111">**Save As**</span></span>  
 <span data-ttu-id="14ce0-112">Enregistre le script dans un fichier texte que vous pouvez enregistrer dans n'importe quel emplacement de votre choix.</span><span class="sxs-lookup"><span data-stu-id="14ce0-112">Saves the script in a text file that you can save in any location you want.</span></span> <span data-ttu-id="14ce0-113">Vous pouvez copier le fichier script vers tout autre serveur en vue de l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="14ce0-113">You can copy the file with the script to any other server to run it there.</span></span>  
  
 <span data-ttu-id="14ce0-114">**Copy**</span><span class="sxs-lookup"><span data-stu-id="14ce0-114">**Copy**</span></span>  
 <span data-ttu-id="14ce0-115">Copie le script dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="14ce0-115">Copies the script to the clipboard.</span></span> <span data-ttu-id="14ce0-116">Vous pouvez ensuite coller le script dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou dans un éditeur de texte pour exécuter des scripts ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="14ce0-116">You can then paste the script into the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor to run the scripts later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14ce0-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14ce0-117">See Also</span></span>  
 [<span data-ttu-id="14ce0-118">Préparer SQL Server pour CDC</span><span class="sxs-lookup"><span data-stu-id="14ce0-118">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
