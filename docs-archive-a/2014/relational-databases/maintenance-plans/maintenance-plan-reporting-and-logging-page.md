---
title: Plan de maintenance (page Création de rapports et enregistrement) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reportinglogging.f1
ms.assetid: 3a30b17a-3deb-446f-900a-62f88934a90f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c7a95a7092ce2cdac4aa0540a5cb57d86b48497
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603977"
---
# <a name="maintenance-plan-reporting-and-logging-page"></a><span data-ttu-id="90180-102">Plan de maintenance, (Page Création de rapports et enregistrement)</span><span class="sxs-lookup"><span data-stu-id="90180-102">Maintenance Plan (Reporting and Logging Page)</span></span>
  <span data-ttu-id="90180-103">La boîte de dialogue **Création de rapport et enregistrement** vous permet de configurer les rapports et les enregistrements qui sont générés lors de l'exécution des plans de maintenance.</span><span class="sxs-lookup"><span data-stu-id="90180-103">Use the **Reporting and Logging** dialog box to configure the reports and logs that are generated when maintenance plans are executed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90180-104">Options</span><span class="sxs-lookup"><span data-stu-id="90180-104">Options</span></span>  
 <span data-ttu-id="90180-105">**Générer un rapport de fichier texte**</span><span class="sxs-lookup"><span data-stu-id="90180-105">**Generate a text file report**</span></span>  
 <span data-ttu-id="90180-106">Indiquez si [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit écrire un rapport de fichier texte.</span><span class="sxs-lookup"><span data-stu-id="90180-106">Specify if you want [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to write a text file report.</span></span>  
  
 <span data-ttu-id="90180-107">**Créer un nouveau fichier**</span><span class="sxs-lookup"><span data-stu-id="90180-107">**Create a new file**</span></span>  
 <span data-ttu-id="90180-108">Crée un nouveau fichier de rapport pour chaque exécution du plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="90180-108">Create a new report file for each execution of the maintenance plan.</span></span> <span data-ttu-id="90180-109">Par défaut, les fichiers de rapport sont enregistrés sur l'ordinateur hébergeant l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contenant ce plan de maintenance, dans le dossier qui a été défini en tant que dossier des journaux par défaut au moment de l'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90180-109">By default, the report files are written to the computer hosting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains this maintenance plan, in the folder established as the default log folder during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup.</span></span> <span data-ttu-id="90180-110">Pour spécifier un autre dossier, entrez le chemin d’accès complet du dossier dans la zone de texte **Dossier** ou cliquez sur le bouton Parcourir ( **...** ) pour naviguer jusqu’au dossier de votre choix.</span><span class="sxs-lookup"><span data-stu-id="90180-110">To specify a different folder, enter the full path of the folder in the **Folder** text box, or click the browse button (**...**) and navigate to the desired folder.</span></span>  
  
 <span data-ttu-id="90180-111">**Ajouter au fichier**</span><span class="sxs-lookup"><span data-stu-id="90180-111">**Append to file**</span></span>  
 <span data-ttu-id="90180-112">Ajoutez le rapport généré pour chaque exécution du plan au fichier spécifié dans la zone de texte **Nom de fichier** .</span><span class="sxs-lookup"><span data-stu-id="90180-112">Append the report from each plan execution to the file specified in the **File name** text box.</span></span> <span data-ttu-id="90180-113">Vous pouvez également spécifier un autre fichier en cliquant sur le bouton Parcourir et en sélectionnant un fichier dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="90180-113">You may also specify a file by clicking the browse button and selecting a file from the dialog box.</span></span>  
  
 <span data-ttu-id="90180-114">**Envoyer le rapport à un destinataire de messagerie**</span><span class="sxs-lookup"><span data-stu-id="90180-114">**Send report to an e-mail recipient**</span></span>  
 <span data-ttu-id="90180-115">Transmet le résultat de l'exécution d'un plan de maintenance par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="90180-115">Transmit the outcome of a maintenance plan execution via e-mail.</span></span> <span data-ttu-id="90180-116">Cette option est uniquement disponible si la messagerie de base de données est activée et correctement configurée.</span><span class="sxs-lookup"><span data-stu-id="90180-116">This option is only available if Database Mail is enabled and properly configured.</span></span>  
  
 <span data-ttu-id="90180-117">**Opérateur d'agent**</span><span class="sxs-lookup"><span data-stu-id="90180-117">**Agent operator**</span></span>  
 <span data-ttu-id="90180-118">Sélectionnez dans la liste l'opérateur d'agent qui sera le destinataire du message électronique.</span><span class="sxs-lookup"><span data-stu-id="90180-118">Select an agent operator from the list who will be the recipient of the e-mail.</span></span> <span data-ttu-id="90180-119">Cette option est uniquement disponible si la messagerie est activée et correctement configurée.</span><span class="sxs-lookup"><span data-stu-id="90180-119">This option is only available if mail is enabled and properly</span></span>  
  
 <span data-ttu-id="90180-120">**Enregistrer les informations étendues**</span><span class="sxs-lookup"><span data-stu-id="90180-120">**Log extended information**</span></span>  
 <span data-ttu-id="90180-121">Permet d'inclure plus d'informations dans le journal.</span><span class="sxs-lookup"><span data-stu-id="90180-121">Include more information in the log.</span></span> <span data-ttu-id="90180-122">L'utilisation de cette option augmente la taille de l'historique du plan de maintenance qui est stocké sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="90180-122">Including this option will increase the size of the stored maintenance plan history.</span></span>  
  
 <span data-ttu-id="90180-123">**Connexion à un serveur distant**</span><span class="sxs-lookup"><span data-stu-id="90180-123">**Log to remote server**</span></span>  
 <span data-ttu-id="90180-124">Enregistre l'historique du plan de maintenance sur un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="90180-124">Logs maintenance plan history to a remote server.</span></span>  
  
 <span data-ttu-id="90180-125">**Connection**</span><span class="sxs-lookup"><span data-stu-id="90180-125">**Connection**</span></span>  
 <span data-ttu-id="90180-126">Spécifie les informations de connexion à utiliser pour se connecter à un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="90180-126">Specifies the connection information to use when logging to a remote server.</span></span>  
  
 <span data-ttu-id="90180-127">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="90180-127">**New**</span></span>  
 <span data-ttu-id="90180-128">Affiche la boîte de dialogue **Propriétés de connexion** .</span><span class="sxs-lookup"><span data-stu-id="90180-128">Displays the **Connection Properties** dialog box.</span></span> <span data-ttu-id="90180-129">Sert à configurer les nouvelles informations de connexion permettant de se connecter à un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="90180-129">Used to configure new connection information for logging to a remote server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90180-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90180-130">See Also</span></span>  
 <span data-ttu-id="90180-131">[Plans de maintenance](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="90180-131">[Maintenance Plans](maintenance-plans.md) </span></span>  
 [<span data-ttu-id="90180-132">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="90180-132">Database Mail</span></span>](../database-mail/database-mail.md)  
  
  
