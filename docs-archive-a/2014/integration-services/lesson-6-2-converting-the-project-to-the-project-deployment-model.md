---
title: 'Étape 2 : Conversion du projet en modèle de déploiement de projet | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80964293-f1f5-4da7-b1fb-00ab8c30c1c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7b879b2bea4afd58a48cdfc6f0890353fe6758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601557"
---
# <a name="step-2-converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="2ecdb-102">Étape 2 : Conversion du projet en modèle de déploiement de projet</span><span class="sxs-lookup"><span data-stu-id="2ecdb-102">Step 2: Converting the Project to the Project Deployment Model</span></span>
  <span data-ttu-id="2ecdb-103">Dans cette tâche, vous allez utiliser l'Assistant Conversion de projet Integration Services pour convertir le projet en modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-103">In this task, you will use the Integration Services Project Conversion Wizard to convert the project to the Project Deployment Model.</span></span>  
  
### <a name="converting-the-project-to-the-project-deployment-model"></a><span data-ttu-id="2ecdb-104">Conversion du projet en modèle de déploiement de projet</span><span class="sxs-lookup"><span data-stu-id="2ecdb-104">Converting the Project to the Project Deployment Model</span></span>  
  
1.  <span data-ttu-id="2ecdb-105">Dans le menu Projet, cliquez sur Convertir en modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-105">On the Project Menu, click Convert to Project Deployment Model.</span></span>  
  
2.  <span data-ttu-id="2ecdb-106">Dans la page d'introduction de l'Assistant Conversion de projet Integration Services, passez en revue les étapes, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-106">On the Integration Services Project Conversion Wizard Introduction page, review the steps then click Next.</span></span>  
  
3.  <span data-ttu-id="2ecdb-107">Dans la page Sélectionner les packages, dans la liste Packages, décochez toutes les cases à l'exception de Lesson 6.dtsx, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-107">On the Select Packages page, in the Packages list, clear all checkboxes except Lesson 6.dtsx then click Next.</span></span>  
  
4.  <span data-ttu-id="2ecdb-108">Dans la page Spécifier les propriétés du projet, cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-108">On the Specify Project Properties page, click Next.</span></span>  
  
5.  <span data-ttu-id="2ecdb-109">Dans la page Mettre à jour la tâche d'exécution de package, cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-109">On the Update Execute Package Task page click Next.</span></span>  
  
6.  <span data-ttu-id="2ecdb-110">Dans la page Sélectionner les configurations, assurez-vous que le package Lesson 6.dtsx est sélectionné dans la liste Configurations, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-110">On the Select Configurations page, make sure the Lesson 6.dtsx package is selected in the Configurations list, then click Next.</span></span>  
  
7.  <span data-ttu-id="2ecdb-111">Dans la page Créer des paramètres, assurez-vous que le package Lesson 6.dtsx est sélectionné et qu'Étendue est définie sur Package, dans la liste Propriétés de configuration, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-111">On the Create Parameters page make sure the Lesson 6.dtsx package is selected, and the Scope is set to Package, in the Configuration Properties List, then Click Next.</span></span>  
  
8.  <span data-ttu-id="2ecdb-112">Dans la page Configurer les paramètres, vérifiez que les valeurs Nom et Valeur sont identiques à celles spécifiées dans la leçon 5 pour la variable et la valeur de configuration, puis cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-112">On the Configure Parameters page verify that the values for Name and Value are the same name and value specified in Lesson 5 for the variable and configuration value, then click Next.</span></span>  
  
9. <span data-ttu-id="2ecdb-113">Dans la page Révision, dans le volet Résumé, notez que l'Assistant a utilisé les informations du fichier de configuration pour définir les propriétés à convertir.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-113">On the Review page, in the Summary pane, notice that the wizard has used the information from the configuration file to set the Properties to be converted.</span></span>  
  
10. <span data-ttu-id="2ecdb-114">Cliquez sur Convertir.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-114">Click Convert.</span></span>  
  
     <span data-ttu-id="2ecdb-115">Lorsque la conversion est terminée, un message avertit que les modifications ne sont pas enregistrées tant que le projet n'est pas enregistré dans Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-115">When the conversion completes a message is displayed warning that the changes are not saved until the project is saved in Visual Studio.</span></span> <span data-ttu-id="2ecdb-116">Cliquez sur OK dans la boîte de dialogue d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-116">Click OK on the warning dialog.</span></span>  
  
11. <span data-ttu-id="2ecdb-117">Dans l'Assistant Conversion de projet Integration Services, cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-117">On the Integration Services Project Conversion Wizard click Close.</span></span>  
  
12. <span data-ttu-id="2ecdb-118">Dans SQL Server Data Tools, cliquez sur le menu Fichier, puis cliquez sur Enregistrer pour enregistrer le package converti.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-118">In SQL Server Data Tools, click the File menu, then click Save to save the converted package.</span></span>  
  
13. <span data-ttu-id="2ecdb-119">Cliquez sur l'onglet Paramètres et vérifiez que le package contient désormais un paramètre pour VarFolderName et que la valeur est le même chemin d'accès que celui spécifié pour le dossier New Sample Data du fichier de configuration de la leçon 5.</span><span class="sxs-lookup"><span data-stu-id="2ecdb-119">Click the Parameters Tab and verify that the package now contains a parameter for VarFolderName and that the value is the same path specified for the New Sample Data folder from the Lesson 5 configuration file.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2ecdb-120">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="2ecdb-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2ecdb-121">Étape 3 : Test du package de la leçon 6</span><span class="sxs-lookup"><span data-stu-id="2ecdb-121">Step 3: Testing the Lesson 6 Package</span></span>](lesson-6-3-testing-the-lesson-6-package.md)  
  
  
