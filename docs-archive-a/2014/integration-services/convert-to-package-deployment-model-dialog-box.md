---
title: Convertir en modèle de déploiement de package, boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.bids.converttolegacydeployment.f1
ms.assetid: 9e60a34a-10f7-48d1-966f-b3ff236ab4b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b52932ad26f8cebd2e67b0025f4b881241119f6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610794"
---
# <a name="convert-to-package-deployment-model-dialog-box"></a><span data-ttu-id="23fd7-102">Convertir en modèle de déploiement de package, boîte de dialogue</span><span class="sxs-lookup"><span data-stu-id="23fd7-102">Convert to Package Deployment Model Dialog Box</span></span>
  <span data-ttu-id="23fd7-103">La commande **Convertir en modèle de déploiement de package** vous permet de convertir un package en modèle de déploiement de package après avoir vérifié la compatibilité du projet et de chaque package du projet avec ce modèle.</span><span class="sxs-lookup"><span data-stu-id="23fd7-103">The **Convert to Package Deployment Model** command allows you to convert a package to the package deployment model after checking the project and each package in the project for compatibility with that model.</span></span> <span data-ttu-id="23fd7-104">Si un package utilise des fonctionnalités propres au modèle de déploiement de projet, par exemple des paramètres spécifiques, le package ne peut pas être converti.</span><span class="sxs-lookup"><span data-stu-id="23fd7-104">If a package uses features unique to the project deployment model, such as parameters, then the package cannot be converted.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="23fd7-105">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="23fd7-105">Task List</span></span>  
 <span data-ttu-id="23fd7-106">La conversion d'un package en modèle de déploiement de package requiert deux étapes.</span><span class="sxs-lookup"><span data-stu-id="23fd7-106">Converting a package to the package deployment model requires two steps.</span></span>  
  
1.  <span data-ttu-id="23fd7-107">Quand vous sélectionnez la commande **Convertir en modèle de déploiement de package** dans le menu **Projet** , le projet et les packages individuels sont examinés dans le but de garantir leur compatibilité avec ce modèle.</span><span class="sxs-lookup"><span data-stu-id="23fd7-107">When you select the **Convert to Package Deployment Model** command from the **Project** menu, the project and each package are checked for compatibility with this model.</span></span> <span data-ttu-id="23fd7-108">Les résultats s’affichent dans le tableau **Résultats** .</span><span class="sxs-lookup"><span data-stu-id="23fd7-108">The results are displayed in the **Results** table.</span></span>  
  
     <span data-ttu-id="23fd7-109">Si le projet ou un package ne réussit pas le test de compatibilité, cliquez sur **Échec** dans la colonne **Résultat** pour obtenir des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="23fd7-109">If the project or a package fails the compatibility test, click **Failed** in the **Result** column for more information.</span></span> <span data-ttu-id="23fd7-110">Cliquez sur **Enregistrer le rapport** pour enregistrer une copie de ces informations dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="23fd7-110">Click **Save Report** to save a copy of this information to a text file.</span></span>  
  
2.  <span data-ttu-id="23fd7-111">Si le projet et tous les packages réussissent le test de compatibilité, cliquez sur **OK** pour convertir le package.</span><span class="sxs-lookup"><span data-stu-id="23fd7-111">If the project and all packages pass the compatibility test, then click **OK** to convert the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23fd7-112">Pour convertir un projet en modèle de déploiement de projet, utilisez **l’Assistant Conversion de projet Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="23fd7-112">To convert a project to the project deployment model, use the **Integration Services Project Conversion Wizard**.</span></span> <span data-ttu-id="23fd7-113">Pour plus d’informations, consultez [Assistant Conversion de projet Integration Services](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="23fd7-113">For more information, see [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23fd7-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="23fd7-114">See Also</span></span>  
 <span data-ttu-id="23fd7-115">[Déploiement de projets et de packages](packages/deploy-integration-services-ssis-projects-and-packages.md) </span><span class="sxs-lookup"><span data-stu-id="23fd7-115">[Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md) </span></span>  
 <span data-ttu-id="23fd7-116">[Déploiement de packages &#40;&#41;SSIS](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="23fd7-116">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="23fd7-117">Assistant Conversion de projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="23fd7-117">Integration Services Project Conversion Wizard</span></span>](../../2014/integration-services/integration-services-project-conversion-wizard.md)  
  
  
