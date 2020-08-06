---
title: Informations d’identification Oracle pour l’exécution d’un script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4a301cb0-2f5b-41ba-81bf-46b41d07f137
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 683b313e5b1065c3709c4637ddf968641612cc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695943"
---
# <a name="oracle-credentials-for-running-script"></a><span data-ttu-id="6059e-102">Informations d'identification Oracle pour l'exécution d'un script</span><span class="sxs-lookup"><span data-stu-id="6059e-102">Oracle Credentials for Running Script</span></span>
  <span data-ttu-id="6059e-103">Pour exécuter le script de journalisation supplémentaire Oracle à partir de la console du concepteur de capture de données modifiées Oracle, le programme vous invite à entrer les informations d'identification de l'utilisateur Oracle qui exécute le script.</span><span class="sxs-lookup"><span data-stu-id="6059e-103">To run the Oracle supplemental logging script from the Oracle CDC Designer console, the program prompts you for the credentials of the Oracle user who is running the script.</span></span> <span data-ttu-id="6059e-104">Pour exécuter ce script, l'utilisateur Oracle doit disposer de l'autorisation ALTER TABLE pour que toutes les tables soient capturées et de l'autorisation SELECT sur la vue DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="6059e-104">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="6059e-105">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="6059e-105">Task List</span></span>  
 <span data-ttu-id="6059e-106">Entrez les informations suivantes dans cette boîte de dialogue :</span><span class="sxs-lookup"><span data-stu-id="6059e-106">Enter the following in this dialog box:</span></span>  
  
 <span data-ttu-id="6059e-107">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="6059e-107">**Authentication**</span></span>  
  
 <span data-ttu-id="6059e-108">Sélectionnez l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="6059e-108">Select one of the following:</span></span>  
  
-   <span data-ttu-id="6059e-109">**Authentification Windows**: sélectionnez cette option pour utiliser les informations d'identification actuelles de domaine Windows.</span><span class="sxs-lookup"><span data-stu-id="6059e-109">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="6059e-110">Vous ne pouvez utiliser cette option que si la base de données Oracle est configurée pour utiliser l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="6059e-110">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="6059e-111">**Authentification Oracle**: si vous sélectionnez cette option, vous devez taper le **Nom d'utilisateur** et le **Mot de passe** de l'utilisateur dans la base de données Oracle source à laquelle vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="6059e-111">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Source Oracle database you are connecting to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6059e-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6059e-112">See Also</span></span>  
 <span data-ttu-id="6059e-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="6059e-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="6059e-114">Examiner et générer des scripts de journalisation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6059e-114">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
