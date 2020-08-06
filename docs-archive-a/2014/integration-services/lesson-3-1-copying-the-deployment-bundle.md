---
title: 'Étape 1 : Copie du bundle de déploiement | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6ef1e56-d278-4a24-afd3-68d8e0595cbb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 326a85a4d04fc22382457b4e2e919f81096ce989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614171"
---
# <a name="step-1-copying-the-deployment-bundle"></a><span data-ttu-id="633c1-102">Étape 1 : Copier le bundle de déploiement</span><span class="sxs-lookup"><span data-stu-id="633c1-102">Step 1: Copying the Deployment Bundle</span></span>
  <span data-ttu-id="633c1-103">Au cours de cette tâche, vous allez copier l'application de déploiement sur l'ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="633c1-103">In this task, you will copy the deployment bundle to the destination computer.</span></span>  
  
 <span data-ttu-id="633c1-104">La méthode la plus simple pour copier l'application de déploiement sur l'ordinateur de destination est de commencer par créer un partage public, mapper un lecteur sur le partage public, puis copier l'application de déploiement sur le partage.</span><span class="sxs-lookup"><span data-stu-id="633c1-104">The easiest way to copy the deployment bundle to the destination computer is to first create a public share on the destination computer, map a drive to the public share, and then copy the deployment bundle to the share.</span></span> <span data-ttu-id="633c1-105">Si vous n'êtes pas certain de la procédure à suivre pour créer et configurer des dossiers publics ou mapper des lecteurs, consultez la documentation Windows.</span><span class="sxs-lookup"><span data-stu-id="633c1-105">If you do not know how to create and configure public folders or map drives, see the Windows documentation.</span></span>  
  
### <a name="to-copy-the-deployment-bundle"></a><span data-ttu-id="633c1-106">Pour copier l'application de déploiement</span><span class="sxs-lookup"><span data-stu-id="633c1-106">To copy the deployment bundle</span></span>  
  
1.  <span data-ttu-id="633c1-107">Accédez à l'application de déploiement sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="633c1-107">Locate the deployment bundle on your computer.</span></span>  
  
     <span data-ttu-id="633c1-108">Si vous avez utilisé l'emplacement par défaut, l'application de déploiement correspond au dossier Bin\Deployment dans le dossier du didacticiel de déploiement.</span><span class="sxs-lookup"><span data-stu-id="633c1-108">If you used the default location, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder.</span></span>  
  
2.  <span data-ttu-id="633c1-109">Cliquez avec le bouton droit sur le dossier Deployment, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="633c1-109">Right-click the Deployment folder and click **Copy**.</span></span>  
  
3.  <span data-ttu-id="633c1-110">Accédez au partage public sur lequel vous souhaitez copier le dossier sur l'ordinateur cible et cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="633c1-110">Locate the public share to which you want to copy the folder on the target computer and click **Paste**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="633c1-111">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="633c1-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="633c1-112">Étape 2 : Exécution de l’Assistant Installation de package</span><span class="sxs-lookup"><span data-stu-id="633c1-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
<span data-ttu-id="633c1-113">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="633c1-113">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="633c1-114">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="633c1-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="633c1-115">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="633c1-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="633c1-116">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="633c1-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
